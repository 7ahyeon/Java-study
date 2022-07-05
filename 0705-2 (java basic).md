# Java-study

**while (반복문)**
- 반복인자의 선언 및 초기값 설정;
- while (실행(종결)조건식) {
- 반복인자값 증감설정
- 실행문(들); }

증감식의 위치에 따라 다른 결과
- 1~9

```java
int num = 1;
while (true) {
	System.out.print(num + " ");
	num++;
	if (num == 10) break;
}
 ```
- 1~10
```java
int num = 1;
while (true) {
	System.out.print(num + " ");
	if (num == 10) break;
	num++;
}
```
