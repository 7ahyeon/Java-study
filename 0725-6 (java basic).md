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

```java
System.out.println("---nextInt()---");

for (int i = 0; i < 10; i++) {
  int ranInt = ran.nextInt();
  System.out.print(ranInt + " ");
}
System.out.println("---nextInt(5)---");

for (int i = 0; i < 10; i++) {
  int ranInt = ran.nextInt(5); // 0~4
  System.out.print(ranInt + " ");
}
```

```java
---nextInt()---
-1713209699 -1120962394 1770165085 2022021387 1306956593 -1040668620 762558927 1984957557 1244957549 157104104 
---nextInt(5)---
4 4 4 1 0 2 1 1 0 4 
```
- Math.random()과 nextDouble()은 차이가 거의 없다.
```java
System.out.println("---nextDouble()---");
		
for (int i = 0; i < 3; i++) {
  System.out.println(ran.nextDouble() + " - Random nextDouble()");
  System.out.println(Math.random() + " - Math.random()");
}
```

```java
---nextDouble()---
0.796530787530322 - Random nextDouble()
0.5336219165513326 - Math.random()
0.7076521709900598 - Random nextDouble()
0.9659010769693918 - Math.random()
0.6363114351740597 - Random nextDouble()
0.53919350999312 - Math.random()
```
