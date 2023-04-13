# sql query statement

- sql query statement 만들기

```sql
SELECT * FROM users;
-- 전체
SELECT first_name, last_name FROM users;
-- 필요한 요소들을 뽑아내는 것

SELECT * FROM users ORDER BY last_name;
-- 순서를 주는 것
SELECT last_name, first_name, balance, age FROM users ORDER BY age, balance DESC;
-- 오름차순, 내림차순을 줄 수도 있고 특정 요소들로만 구성할 수 있다.
SELECT DISTINCT country FROM users;
-- 중복제거
SELECT DISTINCT country, first_name FROM users ORDER BY country;
-- 컴럼들에서 중복들을 다 제거할 때 

SELECT * FROM users WHERE balance > 777777;
-- 조건을 추가해서 특정 요소들을 보여줄 떄
SELECT * FROM users WHERE balance > 777777 ORDER BY balance;
-- 조건을 추가해서 특정 요소들을 보여줄 떄 보기 이쁘게 정렬
-- balance 대신 first_name, last_name 등을 통한 이름 순으로 정렬할 수 도 있다.
SELECT * FROM users WHERE balance < 800000 AND balance > 700000;
-- AND 를 통해 여러 조건을 붙여줄 수 있다.
SELECT * FROM users WHERE balance < 10000 OR balance > 900000;
-- OR도 물론 가능하다.
SELECT * FROM users WHERE balance > 900000;
SELECT * FROM users WHERE last_name = '류';
-- 글자로도 조건들을 찾을 수 있다.
SELECT * FROM users WHERE first_name LIKE '정_';
-- 이름을 찾을 때 wildcard(_)를 통해 특정 단어가 포함된 단어를 조건에 등록해 찾을 수 있다.
SELECT * FROM users WHERE phone LIKE '010-_________';
SELECT * FROM users WHERE phone LIKE '010-%';
SELECT * FROM users WHERE phone LIKE '%77%';
-- %를 사용하여 앞 혹은 뒤에 어떠한 것이 온다면 조건에 충족되게 하는 방법

SELECT * FROM users WHERE age >= 20 AND age < 30 ORDER BY age;
SELECT * FROM users where age LIKE '2_' ORDER BY age;
-- 20대라는 조건을 찾는 경우
SELECT * FROM users where age NOT LIKE '2_' ORDER BY age;
SELECT * FROM users WHERE NOT age >= 20 ORDER BY age;
-- 조건을 제외하고 찾는 경우 NOT의 위치를 생각하면서 사용해보자

SELECT first_name, country FROM users WHERE country in ('경상남도', '경상북도');
-- IN 을 사용하면서 조건을 걸 수 있다.

SELECT * FROM users LIMIT 10;
-- 한번에 다 나오는건 문제가 발생할 수 있기 떄문에 LIMIT를 걸 수 있다.age
SELECT * FROM users ORDER BY age LIMIT 50;
SELECT * FROM users ORDER BY age LIMIT 50 OFFSET 50;
-- 처음 몇개 이후에 리미트 몇개 LIMIT -- OFFSET --
SELECT rowid, last_name, first_name FROM users LIMIT 50 OFFSET 50;
```