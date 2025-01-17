---
title:  "제약조건"
categories: MySQL
excerpt: "not null, unique, primary key, foreign key, check, default, auto_increment, references, restrict, set null, cascade"
---

```sql
-- DB의 제약조건(Constraints)
-- -> 안 쓰는 경우 DB의 무결성을 보장할 수 없음 -> 버그나 에러가 발생함 -> 품질 저하

-- NOT NULL : 특정 컬럼에 NULL을 허용하지 않는 제약 -> 제일 많이 활용되는 제약
-- UNIQUE (U) : 특정 컬럼에 중복 값을 허용하지 않는 제약 // NULL은 벤더사 마다 허용할지 규칙 다름, ORACLE은 허용함
-- PRIMARY KEY (PK) : 테이블의 컬럼중 유일하고 최소로 식별 가능한 데이터를 주키로 설정하는 제약
--                    index 자동으로 활성화(성능이 좋아짐), 보통 sequance key를 활용함
-- FOREIGN KEY (FK) : 외래키, 다른 테이블의 주키를 자신의 테이블의 인자로 활용하여, 
--                    테이블 간 관계를 맺을 때 사용. (종속관계 성립)
-- CHECK : 특정 컬럼의 입력값을 제한하는 제약사항
-- DEFAULT : 해당 컬럼에 입력되는 값이 없는 경우 설정된 초기값으로 값을 저장
-- AUTO_INCREMENT : 고유 번호를 생성하는 문법으로 특정 값을 1부터 자동으로 1씩 증가시킴

-- 제약사항 활용하는 방법
-- 1) 컬럼 레벨에서 제약을 거는 방법 (컬럼명으로 제약) 
-- 2) 테이블 레벨에서 제약을 거는 방법 (테이블명으로 제약)

-- 사용자가 가진 제약을 확인하는 방법
select * from Information_schema.table_constraints;
select * from Information_schema.table_constraints where table_schema = 'global_info';

-- table 레벨에서 제약을 확인하는 방법
desc nation_code;

-- ==================== 제약이 없는 테이블 ====================
create table no_cons_table(
	user_no int -- 컬럼 레벨 제약을 거는 곳 : not null, unique, auto_increment, primary key
    -- 테이블 레벨로 제약을 거는 곳 : unique, primary key, foreign key .. 2개 이상의 컬럼이 필요한 제약
);

-- ==================== NOT NULL이 있는 테이블 ====================
-- NOT NULL : 데이터의 값의 null을 허용하지 않는 제약
create table not_null_table(
	user_no int not null -- not null은 컬럼 레벨에서만 가능
    -- 테이블 레벨에선 not null 제약 선언 불가능
);
insert into not_null_table values(null); -- 실패

-- ==================== unique가 있는 테이블 ====================
-- unique : 컬럼 값 중에 중복을 허용하지 않는 제약
create table unique_table(
	user_no int not null unique, -- 제약을 동시에 거는 방법
    user_id varchar(20) unique,
    user_pw varchar(20),
    user_name varchar(20),
    user_age int,
    -- table 레벨에서 unique 제약 선언하는 곳
    unique(user_name, user_age) -- 이름과 나이가 동시에 일치하는 사람은 가입 불가
);
insert into unique_table values(1, 'id1', 'pw123', '김길동', 20);
insert into unique_table values(2, 'id1', 'pw123', '이길동', 20); -- 실패, user_id 중복
insert into unique_table values(3, 'id3', 'pw123', '박길동', 20);
insert into unique_table values(4, 'id4', 'pw123', '박길동', 20); -- 실패, 이름과 나이가 동시에 일치해 불가

-- ==================== primary key가 있는 테이블 ====================
-- primary key(주키, 기본키, PK)
-- - table의 유일성, 최소성 원칙이 지켜진 id
-- - unique + not null 제약이 발생
-- - 일반적으로 테이블당 1개만 설정
-- - MySQL에서는 PK를 통해 검색 및 삭제, 수정을 진행하는게 좋다. -> 가장 빠르다!
create table pk_table(
	user_no int primary key, -- 컬럼 레벨에서 PK 제약
    user_name varchar(20)
   -- 테이블 레벨에서 제약
   -- primary key(user_no) -- 2개 생성 불가능
);
insert into pk_table values(null, null); -- 실패, pk에 null이 들어갈 수 없음
insert into pk_table values(1, '김길동');
insert into pk_table values(1, '이길동'); -- 실패, pk가 걸린 컬럼에 중복된 데이터를 넣을 수 없음

-- ==================== primary key가 2개인 테이블 ====================
-- 주키 2개 설계 하는 패턴 : 즐겨찾기 (Member PK - Product PK)
create table multi_pk_table(
	user_no int, -- 컬럼 레벨에서는 불가능
   	user_id varchar(20),
   	user_pw varchar(20),
    primary key(user_no, user_id) -- 테이블 레벨에서 2개의 pk 세팅 가능
	-- primary key(user_no, user_id, user_name) -- 3개 이상도 가능
);
insert into multi_pk_table values(1, null, 'pw123'); -- 실패
insert into multi_pk_table values(null, 'id1', 'pw123'); -- 실패
insert into multi_pk_table values(1, 'id1', null);
insert into multi_pk_table values(1, 'id1', 'pw123'); -- 실패
insert into multi_pk_table values(1, 'id2', 'pw123'); -- 성공, pk가 2개 이상일 때 중복 제약은 같이 걸림(unique를 테이블 레벨에서 같이 건 형태)

-- ==================== foreign key가 있는 테이블 ====================
-- foreign key(외래키)
-- 다른 테이블을 참조(join)할 때 다른 테이블의 참조 값(pk)을 자신의 컬럼 값으로 활용할 때 사용
-- 참조무결성을 지킬 수 있다.
-- table 만드는 순서 : 참조될 테이블 -> 참조할 테이블 순으로 작성

-- 사용자 테이블
create table fk_user_table(
	user_no    INT UNIQUE,
    user_id    VARCHAR(20) PRIMARY KEY,   
    user_pw    VARCHAR(20) NOT NULL
);
insert into fk_user_table values(1,'id1','pw123');
insert into fk_user_table values(2,'id2','pw123');

-- 주문 테이블
create table fk_order_table(
	order_no		int primary key,
    product_name	varchar(20) not null,
    product_price	int not null,
    user_id			varchar(20) not null, -- 보통의 외래키는 참조할 테이블의 컬럼명과 일치하는게 정석, 만일 네이밍룰이 안좋다면 바꾼다.
    foreign key(user_id) references fk_user_table(user_id)
);
insert into fk_order_table values (100, '아이폰14', 100, 'id1');
insert into fk_order_table values (101, '아이폰15 Pro', 150, 'id1');
insert into fk_order_table values (102, '아이폰15 Pro', 150, 'id3'); -- 실패, 외래키 제약으로 실패, 참조할 테이블에 id3 없음

select * from fk_order_table join fk_user_table using (user_id);

-- 삭제 테스트
delete from fk_user_table where user_id = 'id1'; -- 외래키 제약으로 삭제 실패-> 참조무결성 위배

-- drop table fk_order_table; -- drop은 create의 역순으로
-- drop table fk_user_table;

-- !!확인 필요 : -- DROP 옵션
-- !!확인 필요 : -- CASCADE : 개체를 변경/삭제할 때, 다른 개체가 참조하고 있을 경우 함께 변경/삭제 됨
-- !!확인 필요 : -- RESTRICT : 개체를 변경/삭제할 때, 다른 개체가 참조하고 있을 경우 변경/삭제가 취소 됨
-- !!확인 필요 : drop table fk_user_table RESTRICT;
-- !!확인 필요 : drop table fk_user_table CASCADE;

-- 외래키가 포함 컬럼 삭제 시 옵션
-- ON DELETE RESTRICTED(디폴트 형태) : 제약으로 인해 child record가 삭제되지 않음, 외래키로 참조된 행 삭제 불가능 -- 제일 안전한 방법
-- ON DELETE SET NULL : 참조된 부분이 null로 채워진다, 외래키가 삭제된 경우 해당 행에 데이터를 NULL 갱신 - 비교적 안전
-- ON DELETE CASCADE : 참조된 부분이 같이 삭제된다, 외래키가 주키로 있는 행이 삭제 되면 참조 된 행도 자동으로 삭제 됨
create table delete_user_table( 
    user_no    INT UNIQUE NOT NULL,
    user_id    VARCHAR(20) PRIMARY KEY,   
    user_pw    VARCHAR(20) NOT NULL
);
insert into delete_user_table values(1,'id1','pw123');
insert into delete_user_table values(2,'id2','pw123');

create table delete_order_table(
    order_no       INT PRIMARY KEY,
    product_name   VARCHAR(20) NOT NULL,
    product_price  INT NOT NULL,
    user_no        INT,
	FOREIGN KEY(user_no) REFERENCES delete_user_table(user_no) 
 -- FOREIGN KEY(user_no) REFERENCES delete_user_table(user_no) ON DELETE SET NULL
 -- FOREIGN KEY(user_no) REFERENCES delete_user_table(user_no) ON DELETE CASCADE 
);
insert into delete_order_table values(100, '아이폰14', '100', 1);
insert into delete_order_table values(101, '아이폰15 프로', '150', 2);

delete from delete_user_table where user_no = 1;

-- ==================== check가 있는 테이블 ====================
-- check 제약 : 정해진 범위의 값을 확인하는 제약
create table check_table(
	user_name varchar(30),
    age int check(age > 19 and age < 40), -- 컬럼 레벨에서의 제약
    gender varchar(2),
    check(gender in('남','여')) -- 테이블 레벨에서의 제약
);
insert into check_table values('홍길동', 8, '남자'); -- 실패, 나이제한
insert into check_table values('홍길동', 20, '남자'); -- 실패, 나이제한은 통과했으나 '남','여'가 아님
insert into check_table values('홍길동', 20, '남');

-- ==================== defualt가 있는 테이블 ====================
-- DEFAULT : 해당 컬럼에 입력 되는 값이 없는 경우 설정된 초기값으로 값을 저장
--           NULL로 초기화하는 경우 default로 값을 지정한 컬럼도 NULL이 됨으로 주의 필요
CREATE TABLE default_table(	
	USER_NO INT PRIMARY KEY,	
	USER_ID VARCHAR(20) DEFAULT '-',	
	USER_PWD VARCHAR(30)
);
insert into default_table (USER_NO) values(0); -- 0	'-'	NULL, 컬럼명을 명시한 insert문법, 표현되지 않은 값은 default값이 적용
insert into default_table values(1, null, null); -- 1 NULL NULL, default옵션이 있어도 null로 값을 넣으면 null이 됨
insert into default_table values(2, default, null); -- 2 '-' NULL, default 명시적 사용

-- ==================== AUTO_INCREMENT가 있는 테이블 ====================
-- AUTO_INCREMENT : 고유 번호를 생성하는 문법으로 특정 값을 1부터 자동으로 1씩 증가 시킴
-- PK 설정시 'XXX_NO INT PRIMARY KEY AUTO_INCREMENT'의 형태를 주로 사용
-- 성능, 편리성, 동시성, 용량, 순번유지 등에서 이점이 있음
DROP TABLE auto_increment_table;
CREATE TABLE auto_increment_table(
	USER_NO INT PRIMARY KEY AUTO_INCREMENT,
	USER_ID VARCHAR(20) DEFAULT '-',
	USER_PWD VARCHAR(30),
	USER_NAME VARCHAR(30) DEFAULT '-'
);
insert into auto_increment_table values(null, default, default, default); -- 1 '-' NULL '-', null을 넣어도 자동증감
insert into auto_increment_table values(10, default, default, default); -- 10 '-' NULL '-', 양수는 그대로 넣어짐
insert into auto_increment_table values(5, default, default, default); -- 5 '-' NULL '-', 양수는 그대로 넣어짐
insert into auto_increment_table values(default, default, default, default); -- 11 '-' NULL '-', default를 넣어도 자동증감, 제일 높은 값으로 부터 +1
ALTER TABLE auto_increment_table AUTO_INCREMENT = 100;
insert into auto_increment_table (USER_NO) values(default); -- 100 '-' NULL '-'
insert into auto_increment_table (USER_NO) values(200); -- 200 '-' NULL '-'
insert into auto_increment_table (USER_NO) values(default); -- 201 '-' NULL '-'
```
