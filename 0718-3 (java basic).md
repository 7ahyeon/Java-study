```java
if (num2 == 0) {
			System.out.println("[예외 발생] 나누는 값이 0입니다");
		} else {
			result = num1 / num2;
			System.out.println("result : " + result);
		}
```
**try ~ catch문**
```java
try {
	result = num1 / num2;
	System.out.println("result : " + result);
} catch(ArithmeticException e) {
	System.out.println("[예외 발생 메시지] 나누는 값이 0입니다");
	System.out.println("[ArithmeticException] e.getMassage() : " + e.getMessage());
} catch(RuntimeException e) {
	System.out.println("[RuntimeException] " + e.getMessage());
} catch(Exception e) {
System.out.println("[Exception] 0으로 나누려고 했습니다");
}
		
```
**try ~ catch ~ finally문**
```java
try {
	print("try문 시작");
	result = 100 / num;

	print("연산 처리 정상 실행");
	print("try문 끝");
	} catch(ArithmeticException e) {
		print("catch문 실행");
	} finally {
		print("finally : 항상 실행(무조건)");
	}
```
- 예외 발생시 return에 의해 finally 구문 뒤 일반 명령문은 실행되지 않음
```java
try {
	print("try문 시작");
	result = 100 / num;

	print("연산 처리 정상 실행");
	print("try문 끝");
} catch(ArithmeticException e) {
	print("catch문 실행");
	return; //main() 메서드 종료하고 호출한 곳으로 되돌아감
} finally {
	print("finally : 항상 실행(무조건)");
}
print("finally 구문 뒤에 작성된 일반 명령문");
```
```java
>> try문 시작
>> catch문 실행
>> finally : 항상 실행(무조건)
```

**throw/throws**
- throw : 예외를 발생시킬 때 사용

```java
throw new ArithmeticException(">>예외 메시지 작성 전달");
throw new ArrayIndexOutOfBonusException(10);
```
```java
	print("연산 시작");

	result = divide(num1, num2);

	System.out.println("divide() 결과 : " + result);
	title("main() 끝");

```
```java
static int divide(int num1, int num2) {
	System.out.println("-> divide() 시작");
	int result = -999;

	try {
		result = num1 / num2;
	} catch(ArithmeticException e) {
		System.out.println("[예외 발생] " + e.getMessage());
	}

	System.out.println("-> divide() 끝");
	return result;
}
```
```java
---main() 시작---
>> 연산 시작
-> divide() 시작
[예외 발생] / by zero
-> divide() 끝
divide() 결과 : -999
---main() 끝---
```
- throws : 발생한 예외 객체를 호출한 곳으로 던질 때(위임/전가) 사용
```java
result = 0;
try {
	result = divThrows(num1, num2);
} catch(ArithmeticException e) {
	System.out.println("[예외 발생] main() divThrows() : " + e.getMessage());

}
System.out.println("divThrows() 연산 결과 : " + result);

title("main() 끝");
```
```java
// RuntimeException 계열 예외는 throws 하지 않아도 됨 (필수X)
// 코드 작성시 예외 처리 필수 아님
static int divThrows(int num1, int num2) throws ArithmeticException{
		System.out.println("-> divThrows() 시작");

		int result = -999;

		try {
			result = num1 / num2;
		} catch(ArithmeticException e) {
			System.out.println("[divThrows() 연산 중 예외 발생] ");
			throw new ArithmeticException("[예외 발생] 0값으로 나누려고 했습니다");
		}

		System.out.println("-> divThrows() 끝");
		return result;

	}
```
```java
	title("main() 시작");

	try {
		firstMethod();
	} catch (MyException e) {
		e.printStackTrace(); // 예외 객체 추적
		print("main-catch문 실행됨");
		System.out.println(">> 오류메시지 : " + e.getMessage());
	}

	title("main() 끝");
```
```java
static void firstMethod() throws MyException {
	title("firstMethod() 시작");
	print("firstMethod() : 실행문");
	secondMethod();
	title("firstMethod() 끝");
}

//throws : 예외를 호출한 곳에서 처리하도록 던짐(예외 처리 전가)
static void secondMethod() throws MyException {
	title("secondMethod() 시작");
	print("secondMethod() : 실행문");
	//예외 발생시키기
	throw new MyException("secondMethod() 예외 발생");

//		title("secondMethod() 끝");
}
	
```
```java
---main() 시작---
---firstMethod() 시작---
>> firstMethod() : 실행문
---secondMethod() 시작---
>> secondMethod() : 실행문
com.mystudy.ex02_myexception.MyException: >> 내가 만든 Exception : secondMethod() 예외 발생
	at com.mystudy.ex02_myexception.MyExcepionTest.secondMethod(MyExcepionTest.java:32)
	at com.mystudy.ex02_myexception.MyExcepionTest.firstMethod(MyExcepionTest.java:23)
	at com.mystudy.ex02_myexception.MyExcepionTest.main(MyExcepionTest.java:9)
>> main-catch문 실행됨
>> 오류메시지 : >> 내가 만든 Exception : secondMethod() 예외 발생
---main() 끝---
```







