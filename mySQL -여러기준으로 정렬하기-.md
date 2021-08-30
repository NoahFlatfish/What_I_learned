# mySQL -여러기준으로 정렬하기-



 `ANIMAL_INS` 테이블이 다음과 같다면

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME  | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | ----- | --------------- |
| A349996   | Cat         | 2018-01-22 14:32:00 | Normal           | Sugar | Neutered Male   |
| A350276   | Cat         | 2017-08-13 13:50:00 | Normal           | Jewel | Spayed Female   |
| A396810   | Dog         | 2016-08-22 16:13:00 | Injured          | Raven | Spayed Female   |
| A410668   | Cat         | 2015-11-19 13:41:00 | Normal           | Raven | Spayed Female   |

동물 보호소에 들어온 모든 동물의 아이디와 이름, 보호 시작일을 이름 순으로 조회하는 SQL문을 작성해주세요. 단, 이름이 같은 동물 중에서는 보호를 나중에 시작한 동물을 먼저 보여줘야 합니다.

정답

~~~mysql
SELECT ANIMAL_ID, NAME, DATETIME
FROM ANIMAL_INS
ORDER BY NAME, datetime DESC
~~~

SELECT ANIMAL_ID, NAME, DATETIME === 고른다 ANIMAL_ID, NAME 그리고 DATETIME

FROM ANIMAL_INS === 어디서? ANIMAL_INS

ORDER BY NAME  === 이름별로 정리하고!

datetime DESC === 같은 이름은 나중에 온 순서대로