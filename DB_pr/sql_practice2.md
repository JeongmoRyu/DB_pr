# sql practice 2

- users의 데이터에서 이름과 나이를 이름을 오름차 순으로 정렬

```sql
SELECT * FROM users;
SELECT first_name, age FROM users ORDER BY first_name, age DESC;
```