# DDL - Table

```
  Create Table <table_name> (
    컬럼 데이터타입 제약조건,
    컬럼2 데이터타입2 제약조건2 ...
  )
```

---

## 데이터타입

> 문자형 데이터 타입

- CHAR(size) : 고정길이 (지정된 길이보다 짧은 데이터 입력시 나머지 공간 공백으로 채워짐)
- VARCHAR(size) : 가변 길이 (지정된 길이보다 짧은 데이터 입력시 나머지 공간 채우지 않음)
- TEXT : 문자열 최대 (65535byte)
- MEDIUMTEXT : 좀더 긴 문자열 (최대 16777215byte)
- LONGTEXT : 더 긴 문자열 (최대 4294967295byte )
- ENUM : 입력가능한 데이터 리스트를 정하고 입력받음

> 숫자형 데이터 타입

- INT (정수형) - TINYINT, SMALLINT, MEDIUMINT
- FLOAT (실수형)
- DOUBLE (사이즈큰 실수형)
- DECIMAL : 고정 소수형 데이터타입 (소수점 사용)

> 날짜형 데이터 타입

- DATE (년도 월 일)
- TIME (시,분,초)
- DATETIME (날짜 시간 형태 기간)
- TIMESTAMP (시스템 변동시 자동으로 시간 저장)
- YEAR (년도)

> 이진 데이터 타입

- BINARY(SIZE) & BYTE(SIZE) : CHAR 형태의 이진데이터 타입
- VARBINARY(SIZE) : VARCHAR 형태의 이진데이터 타입
- BLOB(SIZE) : 이미지 같은거 저장하는 타입
- TINYBLOB, MEDIUMBLOB, LONGBLOB

---

## 제약 조건

- Not Null : column 값에 Null을 가질 수 없다.
- UNIQUE : column 내에 모든 값들 중에 유일해야 한다.(전체 같은 녀석이 없음)
- PRIMARY KEY : Not null + UNIQUE을 합한 형태로 테이블 내에 있는 각 레코드를 구분함.
- FOREIGN KEY : 다른 테이블에서 레코드를 구분할 수 있는 값
- CHECK : 컬럼의 모든 값이 특정 조건을 충족하는지 확인
- DEFAULT : 값이 지정되지 않는 경우 컬럼에 기본값을 설정
- INDEX : DBMS에서 데이터를 매우 신속하게 생성 및 검색을 하는데 사용.

> AUTO_INCREMENT - MYSQL( 번호 하나씩 증가)

---

## 사용예시

```SQL
CREATE TABLE Orders (
  ID int NOT NULL AUTO_INCREMENT,
  OrderNumber int NOT NULL,
  PersonID int,
  OrderDate TIMESTAMP DEFAULT NOW(),
  PRIMARY KEY (ID),
  FOREIGN KEY (PersonID) REFERENCES Persons(ID)
);
```

```SQL
CREATE TABLE Persons (
  ID int NOT NULL AUTO_INCREMENT,
  LastName varchar(255) NOT NULL,
  FirstName varchar(255),
  Age int,
  PRIMARY KEY (ID)
);
```
