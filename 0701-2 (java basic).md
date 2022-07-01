# Java-study

**데이터 data**
1. 입력 input
2. 처리 process
3. 출력 output
- I.O : 입출력

# 반복문

**for문**
- for (초기값 ; 실행(종결)조건 ; 증감설정) {}
- 실행(종결)조건 true일 때 실행문 처리
- -for(; ;) {} : 무한 반복

```java
for (int i = 0; i < 5; i++) {
	System.out.println("*");
}
```
- 실행 순서 : int i = 0 -> i <5 -> System.out.println("*") -> i++
- () 안에서 선언된 변수는 ()밖에서 사용 불가

**예제1 1부터 4까지의 숫자를 출력하시오**
```java
for (int i = 1; i < 5; i++) {
	System.out.println(i);
}
```
