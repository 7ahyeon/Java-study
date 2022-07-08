# Java-stud

**물리적 복사(독립적인 완전한 복제)**
- 배열.clone(), System.arraycopy(), Arrays.copy0f 사용시
- 데이터 저장하고 있는 **객체**를 대상으로 복사 처리
- X
```java
int[][] copyClone = num2dim.clone();
```
- O

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







