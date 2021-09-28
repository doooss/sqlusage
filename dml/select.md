# SELECT

- 데이터베이스의 조회 기능
- 전체 들어갈수 있는 조건들의 순서는 다음과 같다.

```SQL
  SELECT
    <검색할 컬럼명>, <컬럼명2>
  From
    <조회할 테이블>
  WHERE
    <1차 조건문>
  GROUP BY
    <데이터 그룹화>
  HAVING
    <group by 한 데이터의 조건문>
  ORDER BY
    <순서 정렬>

```

---

## WHERE

- select 문에서 1차적으로 조건문을 거는 곳 (비교문이 사용된다.)

- <, >, = 과 같은 기본적인 프로그래밍 비교문이 들어갈 수 있고, 추가적으로 영어 조건문 들이 쓰인다.

```sql
  select City from Persons where Age = 27;

  select * from Persons wehre id < 5;

  select FirstName from Persons where Age>= 30 and Age <= 40

  select FistName from Persons where Age between 30 and 40
```

### AND, OR, NOT

- and , or , Not 과 같은 것들을 활용 할 수도 있다.

```sql
  select FirstName from Persons where Age >= 30 and (City='Busan' or City='Suwon')

  select Age from Persons where Age >= 20 and (City='Gwangju' or City='Daegu')

  select * from Persons where not City='Seoul' and not City='Busan'
```

### Like

- Like는 where 조건에서 특정 패턴을 가진 값을 컬럼에서 찾아내는데 활용된다. (SQL의 정규표현식)

- "%" 는 정규표현식 "\*" 와 유사한 기능을 한다.

- "\_" 는 정규표현식 "." 와 유사한 기능을 한다.

<Center>

|        Like 사용법        |                      설명                      |
| :-----------------------: | :--------------------------------------------: |
|  WHERE column LIKE 'a%'   |           "a"로 시작하는 값을 찾음.            |
|  WHERE column LIKE '%a'   |             "a"로 끝나는 값을 찾음             |
| WHERE column LIKE '%or%'  |       처음과 끝 어디든 "or"인 값을 찾음.       |
| WHERE column LIKE '\_r%'  |         두번째 문자가 "r"인 값을 찾음.         |
| WHERE column LIKE 'a*%*%' | 처음 "a"로 시작하는 3개 글자 이상의 값을 검색. |
|  WHERE column LIKE 'a%o'  |     "a"로 시작해서 "o"로 끝나는 값을 찾음.     |

</Center>

### Like 코드 예시

```sql
  select LastName,FirstName from Persons where City like 'I%'

  select Age from Persons where City like '%n'

  select FirstName from Persons where LastName like 'user%'

  select FirstName from Persons where Age <= 34 and City like 'D%'

  select LastName, FirstName from Persons where FirstName is not null and (City like 'G%' or City like 'S%')

  select * from Persons where LastName like 'user_'
```

### In

- 다수의 값을 조건으로 사용할 수 있게 해주는 명령어

```sql
  SELECT column_name FROM table_name WHERE column_name IN (value1, value2, value3,...)
```

---

## GROUP BY ~ HAVING

- GROUP BY는 출력된 값을 그룹으로 묶고 각 그룹에 대한 요약값 계산시 사용함.
- Having 은 group by 이후에만 사용할 수 있는 조건문으로, Having 으로 그룹화한 값에 조건문을 넣을때 사용

```sql
  select City,count(City) from Persons group by City;

  select City,count(City) from Persons group by City order by count(City) desc;

  select Age,count(Age) from Persons where  Age>=20 group by Age order by Age desc;

  select City, count(City) from Persons group by City having count(City)>=3;

  select City,count(City) from Persons where Age >= 20 group by City having  count(City)>=2 and count(City)<5;
```

---

## ORDER BY

- 정렬 기준을 설정해 주는 작업

- desc, asc 와 함께 사용된다. default 값은 asc 으로 desc인 경우에만 적으면됨

```sql
  SELECT <> FROM <> ORDER BY <정렬 기준> <asc|desc>

  select * from Orders order by PersonID desc;

```

---

## JOIN (FROM 하위속성)

- 데이터를 여러 테이블로 나누어 저장하면 저장 공간을 보다 효율적으로 사용할 수 있고, 조작이 간편하며, 확장하기 편하다.
- 이렇게 여러 테이블로 나눈 후에 하나의 select 문으로 이 데이터들을 얻고자 할 때 사용하는 것이 JOIN 문
- INNER JOIN(교집합), OUTER JOIN(합집합) 이 있다.

> INNER JOIN(교집합)

- 두 테이블을 대상으로 동일성 테스트를 하여 그 결과를 기준으로 집합을 만듬

```sql
  SELECT FirstName,Age,City,OrderNumber,OrderDate FROM Persons INNER JOIN Orders on Persons.ID=Orders.PersonID;
```

> OUTER JOIN (합집합)

- OUTER JOIN 은 한 테이블을 기준으로 다른 테이블의 행과 연결하는 방식을 사용함
- 두 테이블 중 원래의 기준에 따라 LEFT OUTER JOIN , RIGHT OUTER JOIN 으로 나뉨
- 주 축이 되는 데이터 값을 먼저 가져오고 후속 조건에 맞는 데이터들을 추가하는 방식

```SQL
   SELECT FirstName,Age,City,OrderNumber,OrderDate FROM Persons LEFT OUTER JOIN Orders on Persons.ID=Orders.PersonID;

   SELECT FirstName,Age,City,OrderNumber,OrderDate FROM Persons RIGHT OUTER JOIN Orders on Persons.ID=Orders.PersonID;
```
