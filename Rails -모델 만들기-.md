# Rails -모델 만들기-

아이돌 그룹과 엘범으로 모델을 만들어보쟈



### 1:N관계란

* 아이돌 그룹은 매년 앨범을 발매한다. 매년 마다 발매 되는 앨범은 반드시 아이돌 그룹에 의해 발매되니까, **Idol** 과 **Album**은 **1:N관계**라고 말할 수 있다.



### 모델과 테이블 작성

**Idol 모델**과 **idols** 에**테이블**을 만들어주고,

```ruby
rails g model Idol name:string
rake db:migrate
```

**Album 모델**과 **albums**에 **테이블**을 만들어주쟈

```ruby
rails g model Album realease_date:date
rake db:migrate
```



**N**에 해당하는 테이블즉 **album** 이라는 테이블에**xxx_id**라는 **외부키**를 추가해주쟈. **xxx는 1**에 해당하는 **테이블(idol)**의 모델명을 넣어줄 필요가 있다.



기존의 모델이 있는 상태에서 컬럼을 추가해줄때는 이하와같은 방법으로 추가해줄 수 있다.

```ruby
rails g migration add_idol_id_to_albums idol_id:integer
rake db:migrate
```

사실 이전**Album모델**작성시

```ruby
rails g model Order customer_id:integer order_date:date
```

이렇게 먼저 만들어 주어도 상관 없다.



### 각 모델간에 has_many와belogns_to 설정해주기

각 모델간의 관계를 선언하는 방법인 **has_many**와 **belongs_to** 메소드를 사용방법을 배워보쟈

**has_many** 는 **1** 에 해당하는 **모델(Idol)**에다가 복수의 **albums** 를 가진다는 의미로 **has_many** 라고 해주쟈.

 반대로 **belongs_to**는 **N**에 해당하는 **모델(album)**에다가 특정 테이블에 종속된다는 의미로 **belongs_to**라고 해주면 된다 .



```ruby
class Idol < ActiveRecord::Base
  has_many :albums
end
```

```ruby
class Album < ActiveRecord::Base
  belongs_to :idol
end
```



**has_many** 와 **belongs_to** 에는 각각 옵션을 줄 수 있는데 이는 다음과 같다.



#### has_many의 옵션들

| Option name | Description                                                  |
| :---------- | :----------------------------------------------------------- |
| class_name  | 관계되는 모델의 클래스명을 지정가능 관계명과 참조하는 모델의 클래스명을 달리 쓰고싶을때 사용가능 |
| foreign_key | 외부키의 이름을 지정가능 default는 참조하는 모델명_id        |
| dependent   | 부모 오브젝트가 삭제될때의 액션을 정의 destroy,delete_all등 지정가능 |
| as          | polymorphic관계를 정의                                       |
| through     | 모델관계의 설정이가능                                        |



#### belongs_to의 옵션들

| Option name | Description                                                  |
| :---------- | :----------------------------------------------------------- |
| class_name  | 관계되는 모델의 클래스명을 지정가능 관계명과 참조하는 모델의 클래스명을 달리 쓰고싶을때 사용가능 |
| foreign_key | 외부키의 이름을 지정가능 default는 참조하는 모델명_id        |
| dependent   | 부모 오브젝트가 삭제될때의 액션을 정의 destroy,delete등을 지정가능 |
| polymorphic | polymorphic관계를 정의                                       |



https://negabaro.github.io/archive/rails-relation-1-N 참조.