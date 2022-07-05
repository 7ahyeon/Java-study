# Java-study

**while (반복문)**
- 반복인자의 선언 및 초기값 설정;
- while (실행(종결)조건식) {
- 반복인자값 증감설정
- 실행문(들); }

증감식과 break문의 위치에 따라 다른 결과
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

continue문
- 무한 루프를 피하기 위해서 증감식 뒤에 위치
- 1234678910
```java
num = 0;
while (num < 10) {
	num++;
	if (num == 5) continue;
	System.out.print(num);
}
```

**do ~ while**
- 무조건 한 번은 실행

-  반복인자의 선언 및 초기값 설정;
- do {
- 증감설정 (선택적)
- 실행문(들);
- } while (조건식);

- 1~10
```java
int doNum = 1;
do {
	System.out.println("do ~ while : " + doNum);
	doNum++;
} while(doNum <= 10);
```	

```java
doNum = 0;
do {
	doNum++;
	System.out.println("do ~ while : " + doNum);
} while (doNum <= 9);
```
