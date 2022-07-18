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










