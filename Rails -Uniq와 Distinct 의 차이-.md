# Rails 'Uniq' 와 'Distinct'의 차이 



joins 를 사용하면 중복한 값을 처리하기 위해서 필자는 uniq를 수도 없이 시도해봤지만 원하는 결과를 얻을 수 가 없었다. 

정확히 말하자면 uniq 처리 후에, 추가적인 메소드 작성이 되지 않아서 꽤나 많은 시간을 허비했다.

하지만 **Distinct** 를 이용함으로써, 이 문제는 아주 간단하게 해결되었다.



이 둘의 공통점은 **중복값을 제거** 해준다는 것

그래서 **Uniq** 와 **Distinct**의 차이를 작성해보려고 한다.



**Uniq** = **array** method,

**Distinct**는  = **sql** method,



**Uniq** 는 기본적으로 **배열**에 형태로 리턴해준다,

**a = b.joins(:c).uniq**  를 했다고 가정했을때

**a.class = Array** 형식으로 나온다.



**Distinct**는 **ActiveRecord_AssociationRelation** 을 리턴해준다.

**a = b.joins(:c).distinct**  를 사용하다면 

**a.class = ActiveRecord_AssociationRelation** 으로 나온다.



**Uniq** 를 이용한 후에는, 추가적인 **Sql Query** 를 사용하지 못한다.

하지만 **Distinct** 는 추가적인  **Sql Query** 를  작성할 수 있게 해준다.



중복값을 제거 후에 추가적인 작업이 필요하지 않다면 **Uniq**를 사용하고

추가적인 작업이 필요하다면 **Distinct**  사용하도록 하자.