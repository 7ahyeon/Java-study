# Java-study

**예제1 1~10까지의 수 중에서 홀수합 구하기(배열값 사용)**
```java
int[] nums2 = new int[10];
int sum = 0;
for (int i = 0; i < nums.length; i++) {
	nums2[i] = i+1;
	if (nums2[i] % 2 != 0) {
		sum += nums2[i];
	}
}
System.out.println("1~10까지의 수 중에 홀수의 합 : " + sum);
```
**예제2 짝수끼리/홀수끼리 합산(evenSum/oddSum)**
```java
int[] nums3 = new int[10];
int evenSum = 0;
int oddSum = 0;
for (int i = 0; i < nums3.length; i++) {
	nums3[i] = i + 1;
	if (nums3[i] % 2 == 0) {
		evenSum += nums3[i];
	} else {
		oddSum += nums3[i];
		}
}
System.out.println("짝수 합계 : " + evenSum);
System.out.println("홀수 합계 : " + oddSum);
```
**예제3 별**
```java
*
**
***
****
*****

		
char[] ch = {'*', '*', '*', '*', '*'};
		
for (int i = 0; i < ch.length; i++) {
	for (int k = 0; k <= i; k++){
		System.out.print(ch[k]);
	}
	System.out.println();
}
```
