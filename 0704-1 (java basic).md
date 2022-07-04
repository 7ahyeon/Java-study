# Java-study

**for** 몇 번 반복 / **while** 언제까지

짝수 출력

```java
System.out.println("------");
for (int i = 1; i <=10; i++) {
	if (i % 2 == 0) { //짝수 여부 확인
		System.out.println(i);
	}
```

홀수 출력
```java
System.out.println("------");
for (int i = 1; i <=10; i++) {
	if (i % 2 != 0) { //홀수 여부 확인
		System.out.println(i);
	}
```

**제어문** 
- break : 중단 ( 현재 실행중인 반복문을 중단하고 빠져나감 )
- continue : 이어서 계속 ( 다음 반복 실행 )

System.out.println() : 줄바꿈
System.out.print() : 줄바꿈x

예제1. 8 제외 ( continue ) 
```java
for (int i =1; i <= 10; i++) {
	if (i ==8) continue;
	System.out.print(i+" ");
```
	
	
	
	
