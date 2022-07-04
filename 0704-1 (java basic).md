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
	if (i == 8) continue;
	System.out.print(i+" ");
```

예제2. 8 보다 작을 시 출력 ( break ) 
```java
for (int i = 1; i <=10; i++) {
	if(i == 8) break;
	System.out.print(i+" ");
```

예제3. 구구단 
```java
System.out.println("===================");
for (int dan = 2; dan <= 9; dan++){
System.out.println("===" + dan + "단 출력===");
for (int i = 1; i <= 9; i++) {
	System.out.println(dan + " * " + i + " = " + (dan * i));
	}
}

```

예제4. 반복문 사용 * 찍기
```java
for (int i = 1; i <= 5; i++) {
System.out.print("*");
}
```

예제5. 삼각형 그리기  
x  
xx  
xxx  
xxxx  
xxxxx  
  
```java
for (int k = 1; k <= 5; k++) {
	for (int i = 1; i <= k; i++) {
		System.out.print("*");
		}
	System.out.println();
}
```

xxxxx  
xxxx  
xxx  
xx  
x  

```java
for (int i = 1; i <= 5; i++ ) {
	for (int k = 5; k >= i; k--) {
		System.out.print("*");
	}
	System.out.println();
}
```


/////x  
////xx  
///xxx  
//xxxx 
/xxxxx  
 
 ```java
 for (int i = 1; i <= 5; i++ ) {
	for (int k = 5; k >= i; k--) {
		System.out.print(" ");
	}
	for (int d = 1; d <= i; d++) {
		System.out.print("*");}
	System.out.println();
	}
```

xxxxx  
 xxxx  
  xxx  
   xx  
    x  

```java
for (int i = 1; i <= 5; i++ ) {
	for (int k = 1; k <= i; k++) {
		System.out.print(" ");
	}
	for (int d = 5; d >= i; d--) {
		System.out.print("*");}
	System.out.println();
	}
```
