# practice 4

- users의 데이터에서 전화번호 중간 4자리가 77로 시작하고 지역이 ‘경기도’이 아닌 사람들의 이름과 전화번호를 조회하시오.****

```sql
SELECT * FROM users;
SELECT first_name, phone, country FROM users WHERE country NOT IN ('경기도') AND phone LIKE '%-77%-%';
-- '%-77%'을 사용하지 않고 '%-77%-%'을 사용하는 이유는 세번째 자리에 51로 시작하는 경우를 제외하기 위해서이다.
```