# Java-study

**Arrays.copyOf()**
- Arrays.copyOf(int[] original, int newLength)
- Arrays.copyOf(소스 배열, 배열 길이)
- 물리적/데이터 복사 : 다른 객체(독립된 데이터)
```java	
int[] numsCopy = Arrays.copyOf(nums, nums.length);
System.out.println("numsCopy : " + numsCopy);
System.out.println(Arrays.toString(numsCopy));
		
if (nums == numsCopy) {
	System.out.println("> 복사본 동일 개체(주소값 복사)");
} else {
	System.out.println("> 복사본 다른 객체(독립된 데이터)");	
}
```
**Arrays.copyOfRange()**
- Arrays.copyOfRange(int[] original, int from, int to)
- Arrays.copyOfRange(소스 배열, 시작 위치, 마지막 위치 전까지)
```java
int[] numsCopyRange = Arrays.copyOfRange(nums, 0, 3); //[0]부터 [3]이전까지(0부터 3개/[0]~[2])
```		

# 2차원 배열 Two Dimension
**2차원 배열 선언 및 객체 생성**
1. 타입[][] 변수명 = new 타입[크기값][크기값];
2. 타입 변수명[][] = new 타입[크기값][크기값];
3. 타입[][] 변수명 = {{..}, {..}, ..., {..}};
```java
int[][] nums = {{10, 20}, 
		{30, 40},
		{50, 60},
		{70, 80}
		};
System.out.println("nums : " + nums);
System.out.println("nums[0] : " + nums[0]);
System.out.println("nums[0][0] : " + nums[0][0]);
```
```java
nums : [[I@15db9742
nums[0] : [I@6d06d69c
nums[0][0] : 10
```
**nums[i][]길이 출력**
```java
System.out.println("nums.length : " + nums.length);
System.out.println("nums[0].length : " + nums[0].length);
```
**이중 for문으로 2차원 배열 출력**
```java
for (int i = 0; i < nums.length; i++) {
	for (int k = 0; k < nums[i].length; k++) {
		System.out.print(nums[i][k] + " ");
	}
	System.out.println();
}
```
	







