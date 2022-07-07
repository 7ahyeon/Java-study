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
2. **물리적/데이터 복사 :** 깊은 복사 (deep copy)
- 다른 공간에 저장된 데이터 참조
- 서로에게 영향을 주지 않음 (수정 별개)
```java
for (int i = 0; i < num1.length; i++) {
	num2[i] = num1[i];
}
```
3. **System.arraycopy() (물리적 복사)**
- System.arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
- System.arraycopy(소스 배열, 시작 위치, 대상 배열, 대상 시작 위치, 크기)
```java
int[] num2 = new int[num1.length];
System.arraycopy(num1, 0, num2, 0, num1.length);
```
```java
System.arraycopy(num3, 0, num4, 0, 2); // num3에서 num4에 [0]~[1](index 2개 복사)
System.arraycopy(num3, 0, num4, 0, num3.length); 	
```
4. **배열 객체.clone() (물리적 복사)**
```java
int[] num2 = num1.clone();
```

5. **객체 비교**
- 주소값 복사 : 같은 개체 (동일 주소값 참조)
- 물리적/System.arraycopy()/대상 배열.clone() 복사 : 다른 개체 (2개의 독립된 데이터)
```java
if (num1 == num2) {
	System.out.println("같은 객체이다 (동일 주소값 참조)");
} else {
	System.out.println("다른 객체이다(2개의 독립된 데이터)");
}
```

**총정리**
- 배열 값 변경 및 복사
- 문제1 : int 타입의 데이터 3개를 저장할 수 있는 배열num1 생성
1. 10, 20, 30을 입력하고 화면 출력
2. 세번째 데이터를 100으로 변경 후 화면 출력
- 문제2 : num1과 같은 크기의 배열 num1Copy 생성
1. num1 데이터를 num1Copy에 복사 후 화면 출력
2. 주소값 복사인지 데이터 복사(물리적 복사)인지도 확인
```java
package com.mystudy.array4_copy;

public class ArrayCopyExam {

	public static void main(String[] args) {
		
		int[] num1 = new int[3];
		num1 = new int[] {10, 20, 30};
		num1[2] = 100;
		printData("num1", num1);
		printArr("num1", num1);
		
		int[] num1Copy = new int[num1.length];
		
//		주소값 복사

		num1Copy = num1;
		
		printData("num1Copy", num1Copy);
		printArr("num1Copy", num1Copy);
		printObject(num1, num1Copy);
		
		
//		물리적 복사

		num1Copy = new int[num1.length];
		
		for (int i = 0; i < num1.length; i++) {
			num1Copy[i] = num1[i];
		}
		
		printData("num1Copy", num1Copy);
		printObject(num1, num1Copy);
		
		
//		System.arraycopy(소스 배열, 시작 위치, 대상 배열, 대상 시작 위치, 크기)
		
		num1Copy = new int[num1.length];
		System.arraycopy(num1, 0, num1Copy, 0, num1.length);
	
		printData("num1Copy", num1Copy);
		printArr("num1Copy", num1Copy);
		printObject(num1, num1Copy);
		
		
//		배열 대상.clone()
		
		num1Copy = new int[num1.length];
		num1Copy = num1.clone();
	
		printData("num1Copy", num1Copy);
		printArr("num1Copy", num1Copy);
		printObject(num1, num1Copy);
	}
	
	static void printData(String name, int[] arr) {
		System.out.print(name + " : ");
		for (int i = 0; i < arr.length; i++) {
			System.out.print(arr[i] + " ");
			} 
		System.out.println();
	}
	
	static void printArr(String name, int[] arr) {
		System.out.print(name + " : ");
		System.out.println(Arrays.toString(arr));
	}
	
	static void printObject(int[] a, int[] b) {
		if (a == b) {
			System.out.println("같은 객체 (동일 주소값 참조)");
		} else {
			System.out.println("다른 객체 (2개의 독립된 데이터)");
		}
	}
}
```

**printData와 printArr의 차이**
- printData (arr[i])
```java
num1Copy : 10 20 100 
```
- printArr (Arrays.toString(arr))
```java
num1Copy : [10, 20, 100]
```

