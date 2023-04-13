# practice 5

- 잔고가 많은 순서로 조회하고 페이지 당 보여지는 데이터는 50개로 제한했을 때, 3번째 페이지를 조회

```sql
SELECT * FROM users;
SELECT * FROM users ORDER BY balance DESC LIMIT 50 OFFSET 100;
```