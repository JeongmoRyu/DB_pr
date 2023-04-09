# sql make database

환경 변수 설정하기

```sql
1. sqlite3 기본설치 및 환경변수 설정을 합니다.
2. bash 터미널에서 mkdir dbproblem 명령어를 통해 폴더를 생성합니다.
3. cd dbproblem 하여 폴더를 이동합니다.
4. code ~/.bashrc 를 입력하여 .bashrc라는 파일 에디터창을 vscode로 오픈합니다.
5. .bashrc내부에 alias sqlite3="winpty sqlite3" 을 입력하고 저장합니다.
6. vscode 터미널을 열어 source ~/.bashrc를 실행합니다.
6. sqlite3 database.sqlite3 를 입력하여 실습할 데이터베이스를 생성합니다.
7. 이미 database.sqlite3파일이 존재한다면 동일한 명령어 sqlite3 database.sqlite3 를 이용하여 실행합니다.
```

- 데이터베이스 만들고 user.csv 내용 받기

```sql
CREATE TABLE users (
    first_name TEXT NOT NULL,
    last_name TEXT NOT NULL,
    age INTEGER NOT NUll,
    country TEXT NOT NULL,
    phone TEXT NOT NULL,
    balance INTEGER NOT NULL
);
```

```sql
$ sqlite3 db.sqlite3
SQLite version 3.41.2 2023-03-22 11:56:21
Enter ".help" for usage hints.
sqlite> .mode csv
sqlite> .import users.csv users
```