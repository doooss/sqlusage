# DML (Data Manipulation Language) - 데이터 조작어

## 정의

- 정의된 데이터베이스에 입력된 레코드를 조회하거나 수정 삭제하는 역할 하는 언어를 말한다.
- INSERT, UPDATE, DELETE,SELECT 가 여기에 해당

---

## INSERT

- 테이블 내에 데이터를 추가. INSERT INTO 로 묶어서 사용된다. 기본 구조는 다음과 같다

```SQL
  INSERT INTO Persons (ID, LASTNAME, FIRSTNAME) VALUES (101, 'Lee', 'do young') where <조건>
```

- 순서대로 입력한다면 컬럼을 생략해도된다. (테이블의 타입과 순서가 일치해야함)

```sql
  INSERT INTO Persons values (101, 'lee', 'doyoung')
```

- MYSQL 문법 여러개를 입력하는법

```SQL
  INSERT INTO Persons
  (ID,LASTNAME, FIRSTNAME) values (1,'name','name'), (2,'name','name'), ...
```

<!-- 테스트를 안해봄 직접 해보자 -->
<!-- - Oracle에서는 이런 방법을 사용해야한다. 내장 가상 테이블 DUAL 을 이용한 두가지 방법

```sql
  Insert into <table_name> (column1, column2, ... )
    select (value1, value2, ...) from Dual union all
    select (value1, value2, ...) from Dual union all
    select (value1, value2, ...) from Dual union all
    select (value1, value2, ...) from Dual union all
```

```sql
  Insert All
    into table(column1, column2, ...)
      values (value1, value2, ...)
    into table(column1, column2, ...)
      values (value1, value2, ...)
    into table(column1, column2, ...)
      values (value1, value2, ...)
    into table(column1, column2, ...)
      values (value1, value2, ...)
    select * from dual;
``` -->

---

## Update

- 테이블 내의 데이터를 수정하는 법

```sql
  UPDATE table_name SET column1=value1, column2= value2, ... where <조건>
```

---

## Delete

- 테이블 내의 데이터를 삭제

```sql
  DELETE from table_name where <조건>
```

---

## SELECT

- 별도 문서
