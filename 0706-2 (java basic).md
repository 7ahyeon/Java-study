# 배열(Array)
배열의 선언
- 자료형[] 변수명
- 변수에 값 저장 : 배열 변수명[인덱스 번호] = 값;

배열의 선언 및 생성
1. 자료형[] 변수명 = new 자료형[개수];
- (= 자료형 변수명[] = new 자료형[개수];)
```java
int[] arr = new int[5];
System.out.println("arr : " + arr);
System.out.println("arr data: " + Arrays.toString(arr));

arr[0] = 100; //첫번째 data
System.out.println("arr[0] : " + arr[0]);
```
2. 자료형[] 변수명 = new 자료형[]{값1, 값2, ..., 값n};
3. 자료형[] 변수명 = {값1, 값2, ..., 값n}; (n개 저장 공간 생성)
		 
