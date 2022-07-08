# Java-study

**2차원 배열 복사**
- 물리적 복사(독립적인 완전한 복제)
- 배열.clone(), System.arraycopy(), Arrays.copy0f 사용시 데이터 저장하고 있는 **객체**를 대상으로 복사 처리 해야함

- X : 동일 객체
```java
int[][] copyClone = num2dim.clone();
```
- O
```java
for (int d2 = 0; d2 < num2dim.length; d2++) {
	for (int i = 0; i < num2dim[d2].length; i++) {
		num2Copy[d2][i] = num2dim[d2][i];
	}
}
```

**개선된/향상된 for문**
- 타 프로그램 forEach문과 유사
- for (타입 변수명 : 집합 객체) { }

```java
for (int i = 0; i <nums.length; i++) {
	System.out.println(nums[i]);
}
```
```java
for (int num : nums) {
	System.out.println(num);
}
```
**static/instance method**
- 객체 생성 필요 X / O


















