# PRIMARY KEY 조건

특정 Column에 있는 모든 값이 서로 중복되지 않아야 함을 나타내는 조건.

```sql
CREATE TABLE table_name (
	column_name data_type(size) PRIMARY KEY,
	...
)
```

혹은 다음과 같이 나타낼 수 있다.

```sql
CREATE TABLE table_name (
    column_name data_type(size),
    ...
    
    PRIMARY KEY(column_name),
)
```

##예시
|학번|이름|성별|생년월일|거주지|
|:-:|:-:|:-:|:-:|:-:|
|3519|배주웅|남|980327|경기도광주|
|3537|홍영택|남|980716|경기도평택|
|3508|뜨거운 감자남 김정욱|남|980523|감자왕국|

모든 사람이 이름은 있어야 하지만, 이름은 같을 수 있다. 그러나 각 ROW를 구분해야 할 때, 이름이 같다면 둘을 구분하기 힘들 것이다, 그렇기 때문에 PRIMARY KEY를 사용하여, 각 ROW의 **고유 키**를 만드는 것이다.

위 예시에서, 서로 같을 수 없는 Column은 **학번** Column이다. 또한, 학번을 이용해서 각 ROW를 구별할 수 있으므로 **학번은 PRIMARY KEY**로 적합하다. 

만약, 같을 수 없다는 조건을 지키지 않으면 다음과 같은 에러가 난다.

```
ERROR 1062 (23000): Duplicate entry '1' for key 'PRIMARY'
```

