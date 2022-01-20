# mySQL -입양시각구하기-

보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. 09:00부터 19:59까지, 각 시간대별로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 시간대 순으로 정렬해야 합니다.



정답: 

~~~ mysql
SELECT HOUR(DATETIME)AS HOUR,
COUNT(HOUR(DATETIME)) AS COUNT
FROM ANIMAL_OUTS
GROUP BY HOUR
HAVING HOUR BETWEEN 9 AND 19
ORDER BY HOUR
~~~

해설:

SELECT HOUR(DATETIME)AS HOUR,

=> 날짜를 고르고 시간으로 HOUR로 정의함

COUNT(HOUR(DATETIME)) AS COUNT 

=> 시간으로 정의된 날짜를 세주고,  COUNT 정의해줌

FROM ANIMAL_OUTS

=> 어디서?  ANIMAL_OUTS 에서

GROUP BY HOUR

HAVING HOUR BETWEEN 9 AND 19

=> 9~19 사이에 시간들을 묶어준 후

ORDER BY HOUR

=> 시간순으로 정렬해준다
