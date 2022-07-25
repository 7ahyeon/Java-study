# 오늘의 행운지수 알아보기 실습

-  Math.random(), Random 사용해서 행운지수 값 만들기
- 실행결과 출력
- 예) 2022년 7월 25일 당신의 행운지수(0~100)는 77입니다

```java
// 방법 1 - Random nextInt()

Random ran = new Random();
int luk = ran.nextInt(101);
System.out.println("2022년 7월 25일 당신의 행운 지수(0~100)는 " + luk + "입니다.");


// 방법 2 - Math.random()

int luk2 = (int)(Math.random()*100 + 1);
System.out.println("2022년 7월 25일 당신의 행운 지수(0~100)는 " + luk2 + "입니다.");
		
```
```java
2022년 7월 25일 당신의 행운 지수(0~100)는 77입니다.
2022년 7월 25일 당신의 행운 지수(0~100)는 40입니다.

```
