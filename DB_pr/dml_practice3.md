# dml practice 3

```sql
CREATE TABLE user (
    id INT PRIMARY KEY,
    first_name TEXT,
    last_name TEXT NOT NULL,
    age INT NOT NULL,
    country TEXT NOT NUll,
    phone TEXT,
    balance INT NOT NULL
);

INSERT INTO user (id, first_name, last_name, age, country, phone, balance)
VALUES
    (1, '미현', '김', '19', '경기도', '010-211-8482', 300),
    (2, NULL, '최', '33', '제주특별자치도', NULL, 300),
    (3, '미숙', '이', '21', '서울특별시', '010-2122-4958', 480),
    (4, '남석', '박', '18', '경기도', '011-484-8667', 260),
    (5, '철수', '박', '22', '경상남도', '016-295-8989', 500),
    (6, NULL, '박', '45', '전라북도', NULL, 320),
    (7, '민준', '이', '35', '전라남도', '019-965-8833', 350),
    (8, NULL, '남', '24', '충청남도', '010-5882-5969', 210),
    (9, '신', '유', '29', '경상북도', '010-4949-2848', 290),
    (10, NULL, '김', '18', '대전광역시', NULL, 300);

-- 3번
SELECT id, age, balance FROM user WHERE age < 25 ORDER BY age DESC, balance;

-- 4번
SELECT first_name, balance FROM user WHERE first_name NOT NULL AND balance > 400;
-- 문제에서 민준의 계좌 잔고가 350으로 나오고 변화시키는 이야기가 없는데 결과값에 450으로 나오는게 이상한 것 같습니다.

-- 5번
UPDATE user
SET phone='알 수 없음'
WHERE phone is NULL;

SELECT * FROM user;
```