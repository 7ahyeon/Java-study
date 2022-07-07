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
	nums[i] = nums[nums.length-(i+1)];
	nums[nums.length-(i+1)] = temp;
	printArray(nums);
}

```

