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
