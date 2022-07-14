```java
// 일반 자동차
public class Car {

	String type;
	
	void drive() {
		System.out.println(">> 이동");
	}
	void stop() {
		System.out.println(">> 정지");
	}
	
}
```
```java
//구급차 구현
public class Ambulance extends Car{
	
	void siren() {
		System.out.println(">> 응급 환자 이송 사이렌 ~");
	}

}
```
```java
//소방차 구현
public class FireEngine extends Car {

	void siren() {
		System.out.println(">> 화재 경보 출동 사이렌 ~");
	}
	
	void water() {
		System.out.println(">> 화재 진압 ~ ");
	}
}
```
```java
public static void main(String[] args) {
		System.out.println("--- Car 클래스 ---");
		Car car = new Car();
		car.type = "자동차(Car)";
		System.out.println("타입 : " + car.type);
		car.drive();
		car.stop();

		System.out.println("--- Ambulance 클래스 ---");
		Ambulance am = new Ambulance();
		am.type = "구급차(Ambulance)";
		System.out.println("타입 : " + am.type);
		am.drive();
		am.stop();
		am.siren();
	
		System.out.println("--- FireEngine 클래스 ---");
		FireEngine fe = new FireEngine();
		fe.type = "소방차(FireEngine)";
		System.out.println("타입 : " + fe.type);
		fe.drive();
		fe.stop();
		fe.siren();
		fe.water();
```
```java
	System.out.println("\n--- 형변환 ---");
		Car carTemp = new Car(); // Car <- Car
		carTemp.type = "자동차(Car)";
		System.out.println("타입 : " + carTemp.type);
		carTemp.drive();
		carTemp.stop();
//		carTemp.siren(); //undefined : 컴파일 오류 : Car 타입에 siren() 없음
		
		System.out.println("--- Car <- Ambulance 저장 ---");
		// Car <- Ambulance : 상위 타입 <- 하위 타입 (자동 형변환)
		carTemp = am; // Car <- Ambulance : 자동 형변환 //(Car)필요X
		carTemp.drive();
		carTemp.stop();
//		carTemp.siren(); //undefined : 컴파일 오류 : Car 타입에 siren() 없음
		
		print("Ambulance <- Car <- Ambulance");
		// 하위 타입 <- 상위 타입 (명시적(강제) 형변환 처리 필요)
		Ambulance am2 = (Ambulance)carTemp; // Ambulance <- Car //(Ambulance)필요O
		System.out.println("타입 : " + am2.type);
		am2.drive();
		am2.stop();
		am2.siren();
		
		// Ambulance 고유 기능 siren() 사용 : Ambulance 타입이 되어야 함
		// (Ambulance).siren()
		((Ambulance)carTemp).siren();
		
		print("Ambulance <- Car");
		System.out.println("타입 : " + car.type);
		
		// 하위 타입 <- 상위 타입 형변환 : 컴파일 오류X 실행 오류O
		// 실행시 예외 발생 : ClassCastException
//		Ambulance am3 = (Ambulance)car; //명시적(강제) 형변환
//		print("Ambulance <- Car 형변환 후 : " + am3.type);
	
		// 실행시 예외 발생 : ClassCastException
// ((Ambulance)car).siren(); // Car cannot be cast to Ambulance
	
	}
```
