# Java-study

**다형성 Polymorphism**
- 하나의 변수명, 메서드(함수)명 등이 상황에 따라 다른 의미로 해석될 수 있는 것 (메서드 오버로딩, 오버라이딩)
- 상속을 통해 기능을 확장 또는 변경 가능하게 하는 것
- 상속에 의해 생성된 하위 클래스 상위 클래스 타입으로 형변환 가능 : 프로그램 간소화
 
- 상속 관계(extends, implements)에 있는 클래스&클래스, 클래스&인터페이스가 있을 때
- 상위 클래스 = 하위 클래스; //자동형변환 처리됨
- 인터페이스 = 구현클래스; //자동형변환 처리됨
  
- 상위 클래스나 구현한 인터페이스 타입으로 형변환 사용 가능

```java
print("다형성 Polymorphism");
			
		print("타입 확인 후 사용");
		carTemp = car; // Car <- Car
		carTemp = am; // Car <- Ambulance
		carTemp = fe; // Car <-  FireEngine
		
		System.out.println("자동차 타입 : " + carTemp.type);
		
		print("타입 확인 (instanceof)");
		if (carTemp instanceof Object) {
			System.out.println(">> Object 타입");
		}
		
		if (carTemp instanceof Car) {
			System.out.println(">> Car 타입");
			carTemp.drive();
			carTemp.stop();
		}
		
		if (carTemp instanceof Ambulance) {
			System.out.println(">> Ambulance 타입");
			carTemp.drive();
			carTemp.stop();
			((Ambulance) carTemp).siren();
		}
		
		if (carTemp instanceof FireEngine) {
			System.out.println(">> FireEngine 타입");
			carTemp.drive();
			carTemp.stop();
			((FireEngine) carTemp).siren();
			((FireEngine) carTemp).water();
		}
		System.out.println("--------------------------------");
		print("Car 타입 객체 전달시 (타입 체크)");
		typeCheck(car); //Car

		print("Ambulance 타입 객체 전달시 (타입 체크)");
		typeCheck(am); //Ambulance
		
		print("FireEngine 타입 객체 전달시 (타입 체크)");
		typeCheck(fe); //FireEngine
		
		
		
		
	}//main
	
	static void typeCheck(Car car) {
		System.out.println("::: Car 타입이다");
		car.drive();
		car.stop();
		
		if (car instanceof Ambulance) {
			System.out.println("::: Ambulance 타입이다");
			((Ambulance) car).siren();
		}
		
		if (car instanceof FireEngine) {
			System.out.println("::: FireEngine 타입이다");
			((FireEngine) car).siren();
			((FireEngine) car).water();
		}
	}
 ```







