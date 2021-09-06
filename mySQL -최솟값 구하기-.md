#  mySQL - 최솟값 구하기-

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면,

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | -------- | --------------- |
| A399552   | Dog         | 2013-10-14 15:38:00 | Normal           | Jack     | Neutered Male   |
| A379998   | Dog         | 2013-10-23 11:42:00 | Normal           | Disciple | Intact Male     |
| A370852   | Dog         | 2013-11-03 15:04:00 | Normal           | Katie    | Spayed Female   |
| A403564   | Dog         | 2013-11-18 17:03:00 | Normal           | Anna     | Spayed Female   |

정답:

~~~mysql
SELECT min(datetime) from animal_ins
~~~

해설: 

SELECT min(datetime) === 고른다, 가장 작은 날짜

from animal_ins === 어디서? animal_ins에서