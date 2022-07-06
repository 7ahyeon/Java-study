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

arr[5] = 600; //ArrayIndexOutOfBoundsException : 5


// 배열 데이터 합 구하기
int sum = 0;
sum = arr[0] + arr[1] + arr[2] + arr[3] + arr[4];
System.out.println("sum : " + sum);


// 배열 데이터 화면 출력
for (int i = 0; i < 5; i++) { // 5 = index 개수
	System.out.println("arr[" + i + "] : " + arr[i]);


//배열의 크기 값 확인(조회)
System.out.println("arr length : " + arr.length);


//반복문 사용하여 배열값 합계 구하기
sum =0;
for (int index = 0; index <arr.length; index++) {
	sum += arr[index];
}
```
2. 자료형[] 변수명 = new 자료형[]{값1, 값2, ..., 값n};
```java
int[] arr2 = new int[] {100, 101, 102, 103, 104};

System.out.println("arr length2 : " + arr2.length);
for (int i = 0; i < arr2.length; i++) {
	System.out.println(arr2[i]);
		}
```
3. 자료형[] 변수명 = {값1, 값2, ..., 값n}; (n개 저장 공간 생성)
```java
int[] arr3 = {10, 11, 12, 13, 14};
System.out.println("arr3 length2 : " + arr3.length);
		
for (int i = 0; i < arr3.length; i++) {
	System.out.println(arr3[i]);
}
```

```java
// 배열 선언 및 크기 지정
char[] ch = new char[26]; 
ch[0] = 'A'+ 0; //A
ch[1] = 'A' + 1; //B
ch[2] = 'A' + 2; //C
ch[3] = 'A' + 3; //D
		
// 배열에 값 저장
for (int i = 0; i < ch.length; i++) {
	ch[i] = (char)('A' + i);
}
		
// 배열 값 출력(확인)
for (int i = 0; i < ch.length; i++) {
	System.out.println(i + " : " + ch[i]);
}
```

배열 만들고 데이터 저장, 화면 출력
1. 배열 선언 int 값 10개를 저장할 수 있는 배열(nums) 만들기
2. 1~10까지의 수를 배열에 저장(반복문 사용)
3. 배열에 저장된 데이터 화면 출력
- 출력 형태 : 변수명[인덱스 번호] : 값

```java

int[] nums = new int[10];

nums[0] =1; // 값 : 인덱스 번호 + 1
nums[1] =2; // 값 : 인덱스 번호 + 1
		
// 데이터 입력
for (int i = 0; i < nums.length; i++) {
	nums[i] = i + 1;
	}
System.out.println(Arrays.toString(nums));
		
// 배열 값 출력
for (int i = 0; i < nums.length; i++) {
	System.out.println("nums[" + i + "] : " + nums[i]);
}
```

