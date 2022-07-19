# Java-study
```java
public class JumsuOutOfValueException extends SungjukProcessException {

	public JumsuOutOfValueException() {
		super("점수 범위(1-100)를 벗어난 값입니다");
	}

	public JumsuOutOfValueException(String message) {
		super(message);
	}
}
```
```java
public void setEng(int eng) throws JumsuOutOfValueException {
		if (eng >= 0 && eng <= 100) {
			this.eng = eng;
			computeTotAvg();
		} else {
			//System.out.println("[예외] 0~100 범위가 아님");
			throw new JumsuOutOfValueException();
		}
	}
```
```java
System.out.println("---- main() 시작 -----");
		SungjukVO stu = new SungjukVO("홍길동", 100, 90, 81, 0, 0);
		
		stu.setKor(999);
		
		System.out.println(stu.toString());
		
		System.out.println("--- setEng() 처리 ------");
		try {
			stu.setEng(888);
		} catch (JumsuOutOfValueException e) {
			//e.printStackTrace();
			System.out.println(e.getMessage() 
					+ " - 0~100 범위값으로 다시 입력하세요~");
		} catch (SungjukProcessException e) {
			System.out.println("[예외발생] 성적처리가 잘못되었습니다");
		}
		
		System.out.println(stu.toString());
		
		System.out.println("---- main() 끝 -----");
```
```java
---- main() 시작 -----
[오류] 1-100의 범위를 벗어났습니다.
SungjukVO [name=홍길동, kor=100, eng=90, math=81, tot=271, avg=90.33]
--- setEng() 처리 ------
점수 범위(1-100)를 벗어난 값입니다 - 0~100 범위값으로 다시 입력하세요~
SungjukVO [name=홍길동, kor=100, eng=90, math=81, tot=271, avg=90.33]
---- main() 끝 -----
```







