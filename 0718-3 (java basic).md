```java
if (num2 == 0) {
			System.out.println("[예외 발생] 나누는 값이 0입니다");
		} else {
			result = num1 / num2;
			System.out.println("result : " + result);
		}
```
**try~ catch문 처리**
```java
try {
			result = num1 / num2;
			System.out.println("result : " + result);
		} catch(ArithmeticException e) {
			System.out.println("[예외 발생 메시지] 나누는 값이 0입니다");
			System.out.println("[예외 메시지] e.getMassage() : " + e.getMessage());
			
		}
```
