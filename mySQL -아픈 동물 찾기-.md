# mySQL -아픈 동물 찾기-



동물 보호소에 들어온 동물 중 아픈 동물[1](https://programmers.co.kr/learn/courses/30/lessons/59036#fn1)의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.



`ANIMAL_INS` 테이블이 다음과 같다면



| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | -------- | --------------- |
| A365172   | Dog         | 2014-08-26 12:53:00 | Normal           | Diablo   | Neutered Male   |
| A367012   | Dog         | 2015-09-16 09:06:00 | Sick             | Miller   | Neutered Male   |
| A365302   | Dog         | 2017-01-08 16:34:00 | Aged             | Minnie   | Spayed Female   |
| A381217   | Dog         | 2017-07-08 09:41:00 | Sick             | Cherokee | Neutered Male   |



정답

~~~mysql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION = 'Sick'
ORDER BY 'ANIMAL_ID'
~~~



SELECT ANIMAL_ID, NAME  == 고른다,  ANIMAL_ID, NAME 을

FROM ANIMAL_INS == 어디서? ANIMAL_INS 

WHERE INTAKE_CONDITION = 'Sick'  == 어떤애들을?  INTAKE_CONDITION 이  'Sick' 인

ORDER BY 'ANIMAL_ID' = 정리해준다  'ANIMAL_ID 로