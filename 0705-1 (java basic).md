# Java-study

예제 4. 숫자

- 1       : (1 + 빈칸) + 줄바꿈
- 1 2     : (1 + 빈칸) + (2 + 빈칸) + 줄바꿈
- 1 2 3   : (1 + 빈칸) + (2 + 빈칸) + (3 + 빈칸) + 줄바꿈
- 1 2 3 4 : (1 + 빈칸) + (2 + 빈칸) + (3 + 빈칸) + (4 + 빈칸) + 줄바꿈

```java
int dispCnt = 1;
		for (int line = 1; line <= 4; line++) {
			for (int disp = 1; disp <= dispCnt; disp++) {
				System.out.print(disp);
				System.out.print(" ");
			}
			System.out.println();
			dispCnt++;
		}
```

예제 5

- 1    
- 2 3  
- 4 5 6  
- 7 8 9 10

```java

