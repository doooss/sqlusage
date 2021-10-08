# TypeORM

객체 지향 프로그래밍 환경에서 데이터를 다루다 보면, 클래스나 위주로 사용하게 된다. 하지만 RDB(관계형 데이터베이스)의 경우 테이블을 사용하고 있기 때문에 데이터의 모델이 약간 다르다.

이 불일치 성을 해결해 주는 가상의 데이터베이스가 TypeORM 이다.

- 사실상의 가상 데이터베이스를 생성하여 프로그램이 알맞게 컴파일 해주는 것으로 보면 된다.

- TypeORM 은 주로 JS/TS에서 많이 사용 되는 ORM 언어이다.

- 이 폴더에서는 그 TypeORM 의 사용법을 다룰 것이다.

- 코드 테스트 환경은 Nest JS v8.00 , typeorm v0.2.38 , mysql2 v2.3.0 이다

TypeORM은 MySQL, MariaDB, PostgreSQL, CockroachDB, SQLite, MS SQL, Oracle, Mongodb 등의 DB와 연동이 가능하다.
