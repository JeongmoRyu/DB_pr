# dml practice 1

```sql
CREATE TABLE animals (
    animal_name TEXT NOT NULL,
    height INT NOT NULL,
    weight INT NOT NUll,
    age INT
);
--  MEAL칼럽을 추가
ALTER TABLE animals ADD COLUMN meal TEXT;
--  ANIMAL_NAME에서 NAME으로 수정
ALTER TABLE animals RENAME COLUMN animal_name TO name;
--  테이블 명칭을 animals에서 zoo로 수정
ALTER TABLE animals RENAME TO zoo;

DROP TABLE zoo;
-- 아무 것도 뜨지않고 sqlite 명령어를 입력하게 한다.
```