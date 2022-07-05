# Java-study

#자동차 클래스

- 속성 : 차량명, 모델명, 차량 색상, 차량 길이, 차량 폭
- 기능 : 앞으로 이동, 정지, 뒤로 이동, 차량 정보 확인

**final 제한자**
- 변수에 값이 할당되면 더이상 변경 불가
- final 붙은 변수 : 상수화된 변수(상수)

**매개변수 parameter**

**생성자**
- return 타입 없음
- 주의! 명시적으로 생성자 선언시 기본 생성자 만들어주지 않음

1. 클래스명 (){} - 기본 생성자 (default constructor)
2. 클래스명 (매개변수, ...){}

```java
public class Car {

  // 필드 변수(속성) 선언 -----

	String name = "마이카"; //차량명
	String model; //모델명
	String color; //차량 색상
	
	final int CAR_LENGTH = 350;  //차량 길이
	final int CAR_WIDTH = 200;  //차량 폭
	
	
// 생성자 선언 -----
	public Car() {
		model = "드림카";
		color = "무지개색";
	} // 자동 작성 ( 새 생성자 작성시 X / 오류 발생 )
	Car(String n, String m, String c) { 
		name = n;
		model = m;
		color = c;
	}

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
	void dispData() {
		System.out.println("--- 자동차 정보---");
		System.out.println("자동차 이름 : " + name);
		System.out.println("모델명 : " + model);
		System.out.println("색상 : " + color);
		System.out.println("길이 : " + CAR_LENGTH);
		System.out.println("폭 : " + CAR_WIDTH);

		
	}

}
```

CarMain class에서 Car class 호출
- 변수값 변경 가능
- **final 변경 불가능**
- 기본 생성자 public에 선언되어있을시 변경 불가능
```java
public class CarMain {
	public static void main(String[] args) {
	// Car class를 이용하여 객체(≒instance) 생성
		Car car = new Car();
		System.out.println("car : " + car);
		System.out.println("자동차 이름 : " + car.name);
		System.out.println("모델명 : " + car.model);
		System.out.println("색상 : " + car.color);
		System.out.println("길이 : " + car.CAR_LENGTH);
		System.out.println("폭 : " + car.CAR_WIDTH);
		car.name = "드림카"; // 변경 가능
		
		System.out.println("자동차 이름 : " + car.name);
		
//		car.CAR_LENGTH = 400; // final(상수 처리된 변수 값) 변경 불가능
		System.out.println("--- 기능 테스트---");
		car.run();
		car.stop();
		car.back();

		System.out.println("--- car2 만들고 사용 ---");
		Car car2 = new Car("패밀리카", "그랜저", "검정");
		car2.dispData();

	}

}
```

