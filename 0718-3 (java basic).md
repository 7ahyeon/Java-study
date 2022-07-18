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








