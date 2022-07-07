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













