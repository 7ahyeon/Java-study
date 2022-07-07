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
for (int i = 0; i < nums.length; i++) {
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










