# mySQL -동명 동물 수 찾기-

`ANIMAL_INS` 테이블이 다음과 같다면

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME   | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | ------ | --------------- |
| A396810   | Dog         | 2016-08-22 16:13:00 | Injured          | Raven  | Spayed Female   |
| A377750   | Dog         | 2017-10-25 17:17:00 | Normal           | Lucy   | Spayed Female   |
| A355688   | Dog         | 2014-01-26 13:48:00 | Normal           | Shadow | Neutered Male   |
| A399421   | Dog         | 2015-08-25 14:08:00 | Normal           | Lucy   | Spayed Female   |
| A400680   | Dog         | 2017-06-17 13:29:00 | Normal           | Lucy   | Spayed Female   |
| A410668   | Cat         | 2015-11-19 13:41:00 | Normal           | Raven  | Spayed Female   |

동물 보호소에 들어온 동물 이름 중 두 번 이상 쓰인 이름과 해당 이름이 쓰인 횟수를 조회하는 SQL문을 작성해주세요. 이때 결과는 이름이 없는 동물은 집계에서 제외하며, 결과는 이름 순으로 조회해주세요.



정답:

~~~mysql
SELECT NAME, COUNT(NAME) COUNT
FROM ANIMAL_INS
GROUP BY NAME
HAVING COUNT(name) >=2
ORDER BY NAME
~~~



해설:

SELECT NAME, COUNT(NAME) COUNT

=> 이름을 SELECT , COUNT 해주자 => 이름을 지정한 숫자를 세어주자



FROM ANIMAL_INS 

=> 어디서? ANIMAL_INS 



GROUP BY NAME

=> 같은 이름끼 묶어주고



HAVING COUNT(name) >=2

=> 이름 묶음의 개수가 2개 이상인 친구들을



ORDER BY NAME

=> 철자순으로 정리해주자

