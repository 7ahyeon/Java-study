# Java-study

**method overloading**
- 같은 클래스 내에서 같은 이름의 메소드를 축적하는 것
- parameter의 개수, 타입 등을 다르게 함

```java
static void printData(int arr[]) {
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i] + " ");
	}
	System.out.println();
}
	
// method overloading
static void printData(String name, int arr[]) {
	System.out.print(name + " : ");
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i] + " ");
	}
	System.out.println();
}
```

**배열 복사**
1. **주소값 복사 :** 얕은 복사 (shallow copy)
- 참조형이기 때문에 실질적 복사 X
- 같은 공간에 저장된 데이터 참조
- num1[idx] 수정시 num2[idx]도 수정됨

```java
num2 = num1;
num1[0] = 999;
		
printData("num1", num1);
printData("num2", num2);
System.out.println("num1 : " + num1);
System.out.println("num2 : " + num2);
```
2. **물리적 복사 :** 깊은 복사 (deep copy)
- 다른 공간에 저장된 데이터 참조
- 서로에게 영향을 주지 않음 (수정 별개)
```java
for (int i = 0; i < num1.length; i++) {
	num3[i] = num1[i];
}
```
3. **System.arraycopy()**
- System.arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
- System.arraycopy(소스 배열, 시작 위치, 대상 배열, 대상 시작 위치, 크기)
```java
System.arraycopy(num3, 0, num4, 0, 2); // num3에서 num4에 [0]~[1](index 2개 복사)
System.arraycopy(num3, 0, num4, 0, num3.length); 	
```

4. 객체 비교
- 얕은 복사는 같은 개체 : 동일 주소값 참조
- 깊은 복사는 다른 개체 : 2개의 독립된 데이터
```java
if (num3 == num4) {
	System.out.println("같은 객체이다 (동일 주소값 참조)");
} else {
	System.out.println("다른 객체이다(2개의 독립된 데이터)");
}
```




