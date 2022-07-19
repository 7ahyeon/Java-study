# Inner class

**inner class / nested class 내부 클래스**

1. 인스턴스 클래스 (instance class)
- 객체를 생성해야 사용 가능
- 외부 클래스의 필드변수 선언위치에 선언
- 외부 클래스의 인스턴스 변수처럼 취급
- 외부 클래스의 인스턴스 변수들과 관련된 작업에 사용할 목적으로 선언 사용
```java
- 외부 클래스명.내부 클래스명 변수명 = new 외부클래스명().new 내부 클래스명()
- InstanceClass.Inner inner = new InstanceClass().new Inner();
```

2. 스태틱 클래스(static class)
- 클래스의 구성멤버의 일부가 static인 경우 클래스를 static 선언
- 외부 클래스의 필드변수 선언위치에 선언
- 외부 클래스의 static 멤버처럼 사용
- 외부 클래스의 static 멤버와 관련된 작업을 처리하기 위한 경우 사용
  
3. 지역 클래스(local class)
- 외부클래스의 메소드나 초기화 블럭 내에 선언
- 선언된 영역 내부에서만 사용

4. 익명 클래스(anonymous class)
- 클래스의 선언과 객체의 생성을 동시에 하는 이름없는 클래스(일회용)

```java
class 외부클래스 {
	//필드변수
	
	//생성자
	
	//메소드
	void method() {
		class 지역클래스 {
		
		}
	
	}

	class 인스턴스클래스 {
	
	}
	
	static class 스태틱클래스 {
	
	}
	
}
```