# mySQL -동물 수 구하기-

`ANIMAL_INS` 테이블이 다음과 같다면

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | -------- | --------------- |
| A399552   | Dog         | 2013-10-14 15:38:00 | Normal           | Jack     | Neutered Male   |
| A379998   | Dog         | 2013-10-23 11:42:00 | Normal           | Disciple | Intact Male     |
| A370852   | Dog         | 2013-11-03 15:04:00 | Normal           | Katie    | Spayed Female   |
| A403564   | Dog         | 2013-11-18 17:03:00 | Normal           | Anna     | Spayed Female   |

동물 보호소에 동물이 몇 마리 들어왔는지 조회하는 SQL 문을 작성해주세요.



정답:

~~~mysql
SELECT COUNT(ANIMAL_ID)FROM ANIMAL_INS
~~~

해설: 

SELECT COUNT(ANIMAL_ID) === 고른다, 동물의 숫자를

FROM ANIMAL_INS === 어디서? ANIMAL_INS 에서!

