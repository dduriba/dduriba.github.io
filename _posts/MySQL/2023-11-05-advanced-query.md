---
title:  "고급 쿼리"
excerpt: "advanced query"
categories: MySQL
tag: [order by, limit, offset, sum, avg, count, min, max, group by, having, rollup, grouping, union]
classes: wide
---

```sql
-- =========== order by ===========
-- order by : select문에서 나온 결과값을 정렬하는 기능, 명령어 우선순위가 두번째로 낮음 (LIMIT절이 제일 낮음), 날짜,숫자,문자 모두 정렬 가능
select * from nation_code order by nation_name; -- nation_name 컬럼을 기준으로 정렬, 기본값 => asc : 오름차순으로 정렬
select * from nation_code order by nation_name desc; -- 내림차순으로 정렬
select nation_id, nation_name, iso_3166_1 from nation_code order by 2; -- select index 순서로 정렬하는 법, 2번째에 있는 nation_name으로 정렬
select nation_id, nation_name, iso_3166_1 from nation_code order by 2, 1 desc, 3; -- 다중 정렬도 가능, 지정한 순서대로 정렬을 해준다.
select nation_id, nation_name as 국가이름 from nation_code order by 국가이름; -- 별칭으로도 지정 가능

-- =========== limit ===========
-- limit : 조회시 행에 제한을 두고 값을 자르는 기법
--         페이지를 구성하는 경우 특정 순서로 행을 자를 때 사용한다. ex) TOP 5, 최근 게시글 10개 
--         정렬이 되지 않은 상태는 page 구성은 무의미 함으로 정렬 사용이 필수(pk 사용)

select * from nation_code order by nation_id limit 5;

-- =========== offset ===========
-- offset : limit과 결합하여 일정순서를 건너 띄고 조회 가능한 문법 
-- -> 페이징처리 : order by + limit + offset 결합하여 활용
select * from nation_code order by nation_id limit 5 offset 0; -- 1 ~ 5 출력
select * from nation_code order by nation_id limit 5 offset 5; -- 6 ~ 10 출력
select * from nation_code order by nation_id limit 5 offset 10; -- 11 ~ 15 출력

-- offset 생략 문법, 생략시 앞이 offset, 뒤가 limit. 권장하지 않는 문법
select * from nation_code order by nation_id limit 0, 5;
select * from nation_code order by nation_id limit 5, 5;
select * from nation_code order by nation_id limit 10, 5;

-- <=========== GROUP FUNCTION(sum, avg, count, min, max) BEGIN ===========
-- 그룹 함수 : 결과 값이 N:1로 조합되는 함수
-- 			 그룹함수는 DB에서 무거운 기능, 성능적 고려 필요, 느려지는 이유 : 모든 행을 조회해서 지정한 열만 가져오기 때문에 full scaning 된다.

-- =========== sum : 컬럼의 총합을 구하는 함수
select sum(nation_id) from nation_code;

-- =========== avg : 컬럼의 평균을 구하는 함수
select avg(nation_id) from nation_code;

-- =========== count : 컬럼의 갯수를 구하는 함수
select count(nation_id) from nation_code;
select count(nation_id) from nation_code where nation_name like '%of%'; -- of가 들어가는 국가들을 count

-- =========== max : 컬럼의 최대값을 구하는 함수
select max(nation_id) from nation_code;

-- =========== min : 컬럼의 최소값을 구하는 함수
select min(nation_id) from nation_code;
-- =========== GROUP FUNCTION(sum, avg, count, min, max) END===========>

-- =========== group by ===========
-- group by : 그룹함수를 사용할때 그룹핑하여 그룹별로 계산이 가능한 명령어
select country_classification, count(ISO_3166_1) from nation_continent; -- 실패, count-> N:1, nation_name-> N:N
select country_classification, count(ISO_3166_1) from nation_continent group by country_classification; -- group by로 묶어주면 가능

-- where 결합 : select -> from -> where -> group by -> order by 순서
select count(ISO_3166_1) as '국가 선언일이 있는 국가' from nation_independence
where independence_day is not null
group by '국가 선언일이 있는 국가' order by '국가 선언일이 있는 국가';

-- group by 컬럼명, 컬럼명 형태로 세부 그룹으로도 나눌 수 있다.

-- =========== having ===========
-- having : 그룹함수의 결과가 나오고 그 결과에서 조건절을 찾을때 사용하는 방법 (그룹연산시 후행 연산)
-- - where절은 그룹함수가 계산되기 전에 반영됨으로 선행연산이 되고 having절은 그룹함수 이후에 실행
-- - 실행 순서 : where(값 필터링) - 그룹 함수 - having(결과를 다시 조건 반영)
select country_classification, count(ISO_3166_1) as '대륙별_국가_수'
from nation_continent
where country_classification like '%o%' -- where로 대륙이름에 'o'가 들어가는 대륙만 찾음
group by country_classification -- 그룹화
having 대륙별_국가_수 > 2; -- having으로 그룹중에 대륙별 국가 수가 2 이상인 대륙만 조회
-- !'대륙별 국가 수'로 별칭을 지으면 having에선 제대로 인식을 못한다. '' ""를 인식 못하고 띄어쓰기도 인식을 못해서 별칭을 지을 때 띄어쓰기를 _로 대체해주자

-- =========== rollup ===========
-- rollup : 두개의 컬럼 이상을 그룹핑하여 표현할 때 사용, 선언된 그룹 순으로 소계나 총계를 구해오는 기능
select country_classification, ISO_3166_1, count(*)
from nation_continent
group by country_classification, ISO_3166_1
with rollup;

-- =========== grouping ===========
-- grouping 
-- - group by에 산출된 row 경우에는 0을 반환
-- - rollup을 이용해 산출된 row 경우에는 1 이상으로 반환
select country_classification, ISO_3166_1, count(*),
	case when grouping(country_classification) = 0 and grouping(ISO_3166_1) = 1 then '대륙 합계'
		 when grouping(country_classification) = 1 and grouping(ISO_3166_1) = 1 then '조회된 모든 나라 합계'
         else '나라 합계'
	end as 합계
from nation_continent
group by country_classification, ISO_3166_1
with rollup;

-- =========== union, union all ===========
-- union : 집합 연산자
-- - select절의 table이 달라도 컬럼의 갯수와 type만 일치하면 서로 다른 테이블간 결합이 가능
-- - 연산이 느리지만 사용 빈도는 높은 명령어, 테이블간 데이터를 분석 비교할때 유용함
-- - union all 을 사용하면 중복도 포함
select nation_id, nation_name, ISO_3166_1 from nation_code -- 실패, 컬럼 개수가 일치하지 않음
union
select ISO_3166_1, UTC_OFFSET from nation_time;

select ISO_3166_1, nation_name from nation_code
union
select ISO_3166_1, UTC_OFFSET from nation_time;

select nation_id, nation_name, ISO_3166_1 from nation_code where nation_name like '%n%'
union all
select nation_id, nation_name, ISO_3166_1 from nation_code where ISO_3166_1 like '%E%';
```
