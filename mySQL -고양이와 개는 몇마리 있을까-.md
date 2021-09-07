#  mySQL -고양이와 개는 몇마리 있을까-

`ANIMAL_INS` 테이블이 다음과 같다면

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME | SEX_UPON_INTAKE |
| --------- | ----------- | ------------------- | ---------------- | ---- | --------------- |
| A373219   | Cat         | 2014-07-29 11:43:00 | Normal           | Ella | Spayed Female   |
| A377750   | Dog         | 2017-10-25 17:17:00 | Normal           | Lucy | Spayed Female   |
| A354540   | Cat         | 2014-12-11 11:48:00 | Normal           | Tux  | Neutered Male   |

동물 보호소에 들어온 동물 중 고양이와 개가 각각 몇 마리인지 조회하는 SQL문을 작성해주세요. 이때 고양이를 개보다 먼저 조회해주세요.



정답:

```mysql
SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE) COUNT
FROM ANIMAL_INS
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE
```

해설:  

SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE) COUNT 

=>  ANIMAL_TYPE,  에서 SELECT  후,  ANIMAL_TYPE 을 COUNT 해주자.



FROM ANIMAL_INS

=> 어디서?? ANIMAL_INS 에서



GROUP BY ANIMAL_TYPE

=> ANIMAL_TYPE 별로 GROUP BY  를 해줌 => 동물 타입별로 묶어주자



ORDER BY ANIMAL_TYPE

=> ANIMAL_TYPE  별로 ORDER BY 해주자 =>  철자순으로 동물 탑입을 나열해주자

