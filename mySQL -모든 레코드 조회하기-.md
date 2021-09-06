# mySQL -오름차순, 역순 조회하기-



###### 문제 설명

`ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. `ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

| NAME             | TYPE       | NULLABLE |
| ---------------- | ---------- | -------- |
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| INTAKE_CONDITION | VARCHAR(N) | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_INTAKE  | VARCHAR(N) | FALSE    |



순차 정리 =

~~~mysql
SELECT *
from ANIMAL_INS 
ORDER BY `ANIMAL_ID` ASC
~~~

SELECT  *  = 고른다, 전체를

from ANIMAL_INS = 어디서? ANIMAL_INS 테이블에서

ORDER BY `ANIMAL_ID` ASC = 정리해줄거다, animal_id를, 순차적으로 

역순 정리 =

~~~mysql
SELECT *
from ANIMAL_INS 
ORDER BY `ANIMAL_ID` DESC
~~~

SELECT  NAME, DATETIME = 고른다  NAME, DATETIME 을

from ANIMAL_INS = 어디서? ANIMAL_INS 테이블에서

ORDER BY `ANIMAL_ID` ASC = 정리해줄거다, animal_id를, 역순으로 
