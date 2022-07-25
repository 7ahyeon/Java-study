# Random
- 난수(임의의 수)를 생성하는 클래스
- 정수 추출 : nextInt() (정수형 int 타입 난수 생성)
- ex) nextInt(10) : 0~9 범위의 난수 생성 
- 실수 추출 : nextFloat() / nextDouble (실수형 float/double 타입 난수 생성)
- 논리형 추출 : nextBoolean() (false/true 중 하나 생성)

```java
System.out.println("---nextInt()---");
System.out.println("nextInt() : " + ran.nextInt());
System.out.println("nextInt() : " + ran.nextInt());
System.out.println("nextInt() : " + ran.nextInt());

for (int i = 0; i < 10; i++) {
  System.out.print(ran.nextInt(10) + " ");			
}
```
```java
---nextInt()---
nextInt() : -434715691
nextInt() : 1066748527
nextInt() : -222475419
0 8 2 1 3 3 8 9 0 9 
```
```java
System.out.println("---nextFloat()---");
System.out.println("nextFloat() : " + ran.nextFloat());
System.out.println("nextFloat() : " + ran.nextFloat());
System.out.println("nextFloat() : " + ran.nextFloat());
```
```java
---nextFloat()---
nextFloat() : 0.5762371
nextFloat() : 0.83588845
nextFloat() : 0.07898432
```
```java
System.out.println("---nextDouble()---");
System.out.println("nextDouble() : " + ran.nextDouble());
System.out.println("nextDouble() : " + ran.nextDouble());
System.out.println("nextDouble() : " + ran.nextDouble());
System.out.println("nextDouble() : " + ran.nextDouble());
```
```java
---nextDouble()---
nextDouble() : 0.13357712001503674
nextDouble() : 0.5989601475523036
nextDouble() : 0.41005684347654703
nextDouble() : 0.6274714703557835
```
```java
Random ran = new Random();
System.out.println("---nextBoolean()---");
System.out.println("nextBoolean() : " + ran.nextBoolean());
System.out.println("nextBoolean() : " + ran.nextBoolean());

for (int i = 0; i < 10; i++) {
  System.out.print(ran.nextBoolean() + " ");			
}
```
```java
---nextBoolean()---
nextBoolean() : false
nextBoolean() : true
true false false true true false false false true false 
```
