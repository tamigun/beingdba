# ORDER BY & DISTINCT

SELECT 구문과 같이 쓰이 **ORDER BY** 와 **DISTINCT**에 대해 알아보겠다.

##ORDER BY

특정 컬럼 값을 기준으로 정렬하는 것이다. 

|학번|이름|거주지|
|:-:|:-:|:-:|
|3519|배주웅|경기도 광주|
|3502|김동민|경상남도 창원|
|3501|김근호|경기도 안산|
|3515|박유택|서울특별시|
|3537|홍영택|인천광역시|
|3521|신중현|경기도 안산|

이런 테이블이 있을 때, 학번을 기준으로 정렬하고자 하면

```sql
SELECT * FROM student ORDER BY `학번`;
```

으로 하면 번호 순대로 정렬된다. 

|학번|이름|거주지|
|:-:|:-:|:-:|
|3501|김근호|경기도 안산|
|3502|김동민|경상남도 창원|
|3515|박유택|서울특별시|
|3519|배주웅|경기도 광주|
|3521|신중현|경기도 안산|
|3537|홍영택|인천광역시|

문자열도 물론 가능한데, 한글은 한가지 작업을 거쳐줘야 한다. 

```sql
SELECT * FROM student ORDER BY binary(`거주지`)
```
**Column** 이름에 binary 함수를 이용해주면, 아래와 같이 ㄱㄴㄷ 순으로 정렬된다. 

|학번|이름|거주지|
|:-:|:-:|:-:|
|3519|배주웅|경기도 광주|
|3501|김근호|경기도 안산|
|3521|신중현|경기도 안산|
|3502|김동민|경상남도 창원|
|3515|박유택|서울특별시|
|3537|홍영택|인천광역시|

##DISTINCT

중복된 값을 제거하여 출력해준다. 

```sql
SELECT DISTINCT column_name FROM table_name;
```

이렇게 사용하며, 위의 테이블을 이용하여 예시를 보여주겠다. 

```sql
SELECT DISTINCT `거주지` FROM student;
```

|거주지|
|:-:|
|경기도 광주|
|경상남도 창원|
|경기도 안산|
|서울특별시|
|인천광역시|

다음과 같이, 원래 `경기도 안산`이 2개였으나 하나로 줄어서 나온 것을 볼 수 있다. 





