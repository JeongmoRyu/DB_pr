# sql_practice 1

- users 테이블에서 이름, 나이, 계좌 잔고를 나이가 어린 순으로, 만약 같은 나이라면 계좌 잔고가 많은 순으로 정렬

```sql
SELECT * FROM users;
SELECT first_name, age, balance FROM users ORDER BY age, balance DESC;
```