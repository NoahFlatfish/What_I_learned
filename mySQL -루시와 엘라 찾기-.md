# mySQL -루시와 엘라 찾기-

동물 보호소에 들어온 동물 중 이름이 Lucy, Ella, Pickle, Rogan, Sabrina, Mitty인 동물의 아이디와 이름, 성별 및 중성화 여부를 조회하는 SQL 문을 작성해주세요.

```
ANIMAL_INS
```

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE          |
| --------- | ----------- | ------------------- | ---------------- | -------- | ------------------------ |
| A350276   | Cat         | 2017-08-13 13:50:00 | Normal           | Jewel    | Spayed Female            |
| A381217   | Dog         | 2017-07-08 09:41:00 | Sick             | Cherokee | Neutered MaleANIMAL_OUTS |



정답:

~~~ mysql
select animal_id, name, sex_upon_intake
from animal_ins
where name in ('Lucy', 'Ella', 'Pickle', 'Rogan', 'Sabrina', 'Mitty');
~~~



