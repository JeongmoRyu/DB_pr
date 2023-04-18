# dml quiz

```sql
CREATE TABLE zoo (
  name TEXT NOT NULL,
  eat TEXT NOT NULL,
  weight INT NOT NULL,
  height INT,
  age INT
);

INSERT INTO zoo VALUES 
('gorilla', 'omnivore', 215, 180, 5),
('tiger', 'carnivore', 220, 115, 3),
('elephant', 'herbivore', 3800, 280, 10),
('dog', 'omnivore', 8, 20, 1),
('panda', 'herbivore', 80, 90, 2),
('pig', 'omnivore', 70, 45, 5);

BEGIN;
  DELETE FROM zoo
  WHERE weight < 100;
ROLLBACK;
--  무게가 100보다 작은 동물들을 제거한다.
-- 무게가 100보다 작지 않은 동물들은 고릴라, 호랑이, 코끼리가 있다.
--  하지만 ROLLBACK을 하여 다시 6마리로 생각을 한다. 

BEGIN;
  DELETE FROM zoo
  WHERE eat = 'omnivore';
COMMIT;
-- omnivore를 먹는 동물들은 삭제하기에 남은 동물은 호랑이, 코끼리, 판다만 있을 것이다.
-- 정답이 맞기에 COMMIT을 해주면

SELECT COUNT(*)
FROM zoo;
-- 동물원에 남은 동물은 결국 3마리가 있을 것이다.
```