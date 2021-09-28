# DDL (Data Definition Language) - 데이터 정의어

## 정의

- 데이터베이스를 정의하는 언어를 말하며, 데이터를 생성하거나 수정, 삭제 등의 데이터 전체 골격을 결정하는 역할의 언어를 말한다. <br>
- **Create , Alter, Drop, truncate(초기화)** 가 이 부분에 해당된다.

---

## Create

> CREATE <생성할 것> <이름> (내용)

```SQL
   CREATE Database <databasename>

   CREATE user '<userId>@localhost' identified by '<password>'

   CREATE TABLE <table_name> (컬럼 데이터타입 제약조건)
```

## 생성 대상

- Table
- User
- Database
- View
- Index <br>
  ...

---

## Alter

> Alter <객체형식> <객체명> <매개변수>

```SQL
  ALTER TABLE TABLE_NAME ADD COLUMN_NAME DATATYPE;
  ALTER TABLE TABLE_NAME DROP COLUMN COLUMN_NAME
  ALTER TABLE TABLE_NAME MODIFY COLUMN_NAME DATATYPE;
```

---

## Drop

> DROP <객체형식> <객체명>

```SQL
  DROP TABLE TABLE_NAME
  DROP USER USER_NAME
  DROP DATABASE DATABASE_NAME
```

## Truncate

> Truncate <객체형식> <객체명>

```SQL
  TRUNCATE TABLE TABLE_NAME
```
