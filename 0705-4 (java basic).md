# Java-study

자동차 클래스
- 속성 : 차량명, 모델명, 차량 색상, 차량 길이, 차량 폭
- 기능 : 앞으로 이동, 정지, 뒤로 이동, 차량 정보 확인

**final 제한자**
- 변수에 값이 할당되면 더이상 변경 불가
- final 붙은 변수 : 상수화된 변수(상수)

```java
public class Car {

  // 필드 변수(속성) 선언 -----

	String name = "마이카"; //차량명
	String model; //모델명
	String color; //차량 색상
	
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

CarMain class에서 Car class 호출
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
	}

}
```

