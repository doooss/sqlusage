# DCL (Data Control Language) - 데이터 제어어

## 정의

- 데이터베이스에 접근하거나 객체에 권한을 주는 등의 역할을 하는 언어를 말한다.
- **GRANT , REVOKE, COMMIT , ROLLBACK** 이 여기에 속한다

---

## GRANT

- 권한을 부여작업

```SQL
  GRANT ALL PRIVILEGES ON DB_NAME.TABLE_NAME TO USERID@HOST;
```

```SQL
  GRANT all privileges on *.* to userid@localhost (로컬에서 모든 DB 및 테이블에 접근 권한 설정)
  GRANT all privileges on *.* to userid@'%' (모든 DB 및 테이블에 대하여 사용자에게 권한을 주고 원격접속 허용)
  GRANT all privileges on testDB.Persons to userid@'%'('testDB' 에 대한 접근 및 Person테이블에 대한 접근 권한 설정)
```

---

## REVOKE

- 권한 박탈,회수

```SQL
  REVOKE all on db_name.table_name from userid@host;
```

---

## COMMIT

- 트렌젝션의 작업이 완료되었음을 관리자에게 전달

---

## ROLLBACK

- 트렌젝션 작업이 비정상으로 종료될 경우 상태 복구
