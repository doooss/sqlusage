# Entity

TypeORM을 거쳐서 DB에 접근하는 경우, 그 데이터에 대해 정의 해줄 필요가 있다.

그러한 작업을 도와주는 것이 _@Entity_ 이며 그를 이용한 예제가 아래에 있다.

```ts
import { Entity, PrimaryGeneratedColumn, Column } from "typeorm";

@Entity()
export class Person {
  // @PrimaryColumn()
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @Column()
  companyName: string;

  @Column()
  age: number;
}
```

> Entity 안에는 option으로 테이블 명을 정할수 있다. 정하지 않으면 class 명이 테이블 명이 된다.

```ts
@Entity('테이블명')
```

> SQL 문에서는 데이터 입출력에서 길이를 선언한다. TypeORM에서 길이를 선언하고 싶다면 컬럼안에 {length : } 로 넣으면 된다

```ts
  @Column({length : 30})
  name : string;
```

> PrimaryKey가 자동으로 생성되도록 설정할 수 있으며, _@PrimaryColumn_ 으로 사용하는 경우 데이터 생성시 중복되지 않게 넣는 과정이 필요하다.

```ts
  @PrimaryGeneratedColumn()
  id: number;

// 아래 경우 create 과정에서 id 값을 넣어주어야 함
  @PrimaryColumn()
  id: number;
```

> 추가적인 데코레이터로 _@CreateDateColumn()_ _@UpdateDateColumn()_ 과 같은 기능이 있다.

```ts
// 컬럼생성시 타임스탬프
  @CreateDateColumn()
  createDate: number;
//  업데이트시 타임스탬프
  @UpdateDateColumn()
  updateDate: number;
```
