# DDL Debugging

```sql
CREATE TABLE zoo (
  name TEXT NOT NULL,
  eat TEXT NOT NULL,
  weight INT NOT NULL,
  height INT,
  age INT
);

-- 1) 
INSERT INTO zoo (age, weight, height, name, eat)
VALUES (5, 180, 210, 'gorilla', 'omnivore');
-- 순서에 맞도록 정렬하고 VALUES를 제공해준다.

-- 2)
INSERT INTO zoo (height, name, eat, weight, age) VALUES
(10,'dolphin', 'carnivore', 210, 3),
(10, 'alligator', 'carnivore', 250, 50);
-- rowid는 컬럼에 없기에 키로 변경해준다.

-- 3)
INSERT INTO zoo (name, eat, age, weight) VALUES
('dolphin', 'carnivore', 3, 200);
-- 이름, 주식, 무게는 필수이기에 넣어준다.
```