# Java-study
**배열값 화면 출력 method**
- main end/class end 사이에 생성
```java
static void printArray(int[] arr) {
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i] + " ");
	}
	System.out.println();
}
```

**변수값 서로 교환하기**
```java
int temp = 0;
temp = nums[0];
nums[0] = nums[4];
nums[4] = temp;
```
```java
// 배열 데이터 수와 관계 없이 데이터를 뒤집는 로직 작성
int temp = 0;
for (int i = 0; i < nums.length / 2; i++) {
	temp = nums[i];
	nums[i] = nums[nums.length-(i+1)]; //i++사용시 i값이 변경되므로 사용X
	nums[nums.length-(i+1)] = temp;
	printArray(nums);
}
```
- i+1 != ++i/i++
- i+1은 i값이 변하지 않지만 ++i/i++는 i값을 변경하므로 같지 않다.

**배열값 변경**
```java
int[] nums = {100, 200, 300, 400, 500};
nums = new int[] {100, 200, 300, 400, 500, 600};
```
**Math.random()**
- 0 ~ 1 미만의 **실수형** 데이터 리턴
- 0.000 ~ 0.9999
- (int)(Math.random()*n) : 0부터 n-1까지의 정수
```java
int rNum = (int)(Math.random()*45); //0부터 44까지의 숫자
System.out.println("랜덤 숫자(0~44) : " + rNum);
```
		

**예제1. 로또 번호 생성기
1. int 타입의 숫자 45개 저장할 수 있는 배열 타입 변수(balls)
2. 초기화 : 1~45까지의 숫자(번호) 입력
3. 섞음 (Math.random() 사용)
4. 앞에서부터 6개 번호 호출
```java
//1. int 타입의 숫자 45개 저장할 수 있는 배열 타입 변수(balls)
int[] balls = new int[45];
		
//2. 초기화 : 1~45까지의 숫자(번호) 입력
for (int i = 0; i < balls.length; i++) {
	balls[i] = i+1;
}

//3. 섞음 (Math.random() 사용)
int rNum = (int)(Math.random()*45);
int temp = 0;
for (int i = 0; i < 10000; i++) {
	rNum = (int)(Math.random()*45);
	temp = balls[0];
	balls[0] = balls[rNum];
	balls[rNum] = temp;
}		
System.out.println();
System.out.print(">> 로또 추첨 결과 (1등) : ");

//4. 앞에서부터 6개 번호 호출
int call = 6;
for (int i = 0; i < call; i++) {
	System.out.print(balls[i] + " ");
}
System.out.println();
System.out.println(">>추첨 끝");
```










