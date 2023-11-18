---
title:  "테이블 만들기"
excerpt: "create table"
categories: MySQL
tag: [create table]
classes: wide
---

```sql
-- 문자형
-- CHAR(길이) : 길이 고정형 문자열, 지정한 수만 크기를 지정하여 공간을 확보하는 변수, 최대 256 글자
-- VARCHAR(길이) : 가변형 문자열, 선언한 크기만큼 공간이 늘어 날수 있다. (실제는 사용한 크기만큼 할당) 최대 65,535글자
-- TEXT : VARCHAR와 같은 크기의 문자열 저장 Type (65,535 byte), disk 텍스트를 저장할 때 사용
-- MEDIUMTEXT : VARCHAR보다 더 많은 문자열이 저장 가능 (16,777,215 byte, 16MB)
-- LONGTEXT : VARCHAR보다 더 많은 문자열이 저장 가능 (4,294,967,295 byte, 4GB)
--  ※ 주의 : TEXT류는 데이터를 disk 저장하여 느려지고, 크기 제한이 되지 않음. VARCHAR를 최우선 사용하고 가급적 선언하지 말 것!

-- 숫자형
-- INT : 정수형으로 사용하는 일반 Type (4byte, +-21억)
-- BIGINT : long type 정수형으로 사용하는 일반 Type (8byte)
-- DOUBLE : 실수를 사용할 때 사용하는 표준 Type
-- DECIMAL : 고정소수점을 정교하게 활용할 때 사용하는 방법, DECIMAL(정수 길이, 소수점 길이)로 길이 제한이 가능
-- BOOL : true / false

-- 날짜형
-- DATE : 날짜만 저장하는 Type
-- TIME : 시간만 저장하는 Type
-- DATETIME : 날짜 시간 모두 저장하는 Type
-- TIMESTAMP : 날짜 시간 모두 저장하고, 실제 정수형으로 저장되어 데이터 저장 및 insert가 빠름 -> log성 데이터는 해당 Type으로 저장

-- 데이터형 : BLOB, MEDIUMBLOB, LONGBLOB
-- 바이너리 데이터 저장 가능(사진, 동영상, 기타 등등의 확장자)
-- ※ File은 웬만하면 DB에 저장하지 않고, 경로만 저장하는 게 일반적

-- DROP SCHEMA global_info;
CREATE SCHEMA global_info;
USE global_info;

CREATE TABLE nation_code  (
    NATION_ID INT PRIMARY KEY AUTO_INCREMENT comment '인덱스', 
    NATION_NAME VARCHAR(20) NOT NULL comment '국가이름', 
    ISO_3166_1 CHAR(2) NOT NULL comment '국가코드'
);

-- desc nation_code;
   
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '대한민국', 'KR');
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '일본', 'JP');
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '미국', 'US');
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '중국', 'CN');
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '캐나다', 'CA');
Insert into nation_code (NATION_ID, NATION_NAME, ISO_3166_1) values (null, '영국', 'GB');

-- select * from nation_code;

CREATE TABLE nation_time  (
	ISO_3166_1 CHAR(2) PRIMARY KEY NOT NULL comment '국가코드',
    UTC_OFFSET int NOT NULL comment 'UTC 시간 차이'
);

-- desc nation_time;

Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('KR', +9);
Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('JP', +9);
Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('US', -5);
Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('CN', +8);
Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('CA', -5);
Insert into nation_time (ISO_3166_1, UTC_OFFSET) values ('GB', 0);

-- select * from nation_time;

COMMIT; -- insert를 수행하는 경우 DB에 완전히 저장하기 위해선 commit이 필요
```
