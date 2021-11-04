# mySQL -입양시각구하기2-

보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. 0시부터 23시까지, 각 시간대별로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 시간대 순으로 정렬해야 합니다.

정답: 

~~~ mysql
WITH RECURSIVE TIMETABLE(HOUR) AS (
    SELECT 0
    UNION
    SELECT TIMETABLE.HOUR + 1 FROM TIMETABLE WHERE TIMETABLE.HOUR < 23
)

SELECT HOUR, COUNT(A.ANIMAL_ID)
FROM TIMETABLE AS T LEFT JOIN ANIMAL_OUTS AS A ON T.HOUR = HOUR(A.DATETIME)
GROUP BY HOUR
ORDER BY HOUR
~~~

