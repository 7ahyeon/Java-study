# Java-study

자동차 클래스
- 속성 : 차량명, 모델명, 차량 색상, 차량 길이, 차량 폭
- 기능 : 앞으로 이동, 정지, 뒤로 이동, 차량 정보 확인

```java
public class Car {

  // 필드 변수(속성) 선언 -----

	String name = "마이카"; //차량명
	String model; //모델명
	String color; //차량 색상
	
	// final 제한자: 변수에 값이 할당되면 더이상 변경 불가
	// final 붙은 변수 : 상수화된 변수(상수)
	final int CAR_LENGTH = 350;  //차량 길이
	final int CAR_WIDTH = 200;  //차량 폭
	
	
	// 생성자 선언 -----
	//public Car() {}


	// 메소드(동작/기능/함수) 선언 -----
	
	void run() {
		System.out.println(">>앞으로 이동");
	}

	void stop() {
		System.out.println(">>멈춤");
	}

	void back() {
		System.out.println(">>뒤로 이동");
	}



}
```
