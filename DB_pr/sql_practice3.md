# sql practice 3
WHERE(조건)

- users의 데이터에서 이름이 ‘건마’고, 지역 정보가 ‘서울’ 인 데이터를 조회하시오.
- users의 데이터에서 경상남도, 경상북도에 살지 않는 사람들 중 나이가 20살 이상, 30살 보다 적은 사람들의 데이터를 나이를 기준 내림차순으로 조회하시오.

```sql
SELECT * FROM users;
SELECT first_name, country FROM users WHERE first_name LIKE '건마' AND country LIKE '서울';
SELECT * FROM users WHERE country NOT IN ('경상남도', '경상북도') AND age >= 20 AND age < 30 ORDER BY age DESC;
SELECT * FROM users WHERE country NOT IN ('경상남도', '경상북도') AND age LIKE '2_' ORDER BY age DESC;
```