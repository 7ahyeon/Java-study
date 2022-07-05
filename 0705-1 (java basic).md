# Java-study

예제 1. 숫자(반복)

- 1       : (1 + 빈칸) + 줄바꿈
- 1 2     : (1 + 빈칸) + (2 + 빈칸) + 줄바꿈
- 1 2 3   : (1 + 빈칸) + (2 + 빈칸) + (3 + 빈칸) + 줄바꿈
- 1 2 3 4 : (1 + 빈칸) + (2 + 빈칸) + (3 + 빈칸) + (4 + 빈칸) + 줄바꿈

```java
int dispCnt = 1;
for (int line = 1; line <= 4; line++) {
	int dispNum = 1;
	for (int disp = 1; disp <= dispCnt; disp++) {
		System.out.print(dispNum + " ");
		dispNum++;
	}
	System.out.println();
	dispCnt++;
}
```

예제 2. 숫자(나열)

- 1    
- 2 3  
- 4 5 6  
- 7 8 9 10

```java
dispCnt = 1;
int dispNum = 1;
for (int line = 1; line <= 4; line++) {
	for (int disp = 1; disp <= dispCnt; disp++) {
		System.out.print(dispNum + " ");
		dispNum++;
	}
	System.out.println();
	dispCnt++;
}
```

예제 3. 배수

```java
System.out.print("27의 배수 : ");
for (int num = 2000; num <= 3000; num++) {
	if (num % 27 == 0)
		System.out.print(num +" ");
}
```

예제 4. 배수의 개수

```java
int count = 0;
for (int num = 2000; num <= 3000; num++) {
	if (num % 27 == 0) count++;
}
System.out.print("27의 배수 개수: " + count);
```

예제 5. 정리

```java
int startNum = 90;
int endNum = 300;
int divNum = 7;
		
System.out.print( divNum + "의 배수 : ");
for (int num = startNum; num <= endNum; num++) {
	if (num % divNum == 0)
		System.out.print(num +" ");
```

예제 6. 구구단
- "\t" : Tab

```java
int startNum = 1;
int endNum = 9;
int startDan = 2;
int endDan = 9;
for (int num = startNum; num <= endNum; num++) {
	for (int dan = startDan; dan <= endDan; dan++) {
		System.out.print(dan + "*" + num + "=" +(dan * num) + "\t");
		}
System.out.println();
}
```


