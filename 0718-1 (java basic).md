
**DTO (Data Transfer Object)**
- 데이터(값)을 저장하고 전송하기 위한 클래스(객체)
- 명명 : Student, StudentDTO, StudentDto

# 숫자 3개 중 가장 큰 수 구하기 최대값 찾기 실습
```java
int max = Integer.MIN_VALUE;

int[] num = {30, 60, 20};
for (int i = 0; i < num.length; i++){
  if (num[i] > max) {
    max = num[i];
    }
}
System.out.println(">> 가장 큰 수 : " + max);			
```

# 숫자 5개 중 가장 큰 수 구하기 최대값 찾기 실습

```java
int[] num2 = {30, 60, 20, 15, 70};
for (int i = 0; i < num2.length; i++){
  if (num2[i] > max) {
    max = num2[i];
  }
}
System.out.println(">> 가장 큰 수 : " + max);			
```
# method overloading vs overriding

**메서드 오버로딩 method overloading**
- 중복 선언 / 동일 기능
- 다른 메서드 동일 메서드명 사용 가능
- 1개 클래스 내에서 적용 (상속 X)
- printBoolean(boolean), printInt(int), ... , printObject(object) : print()
```java
sound(cat);
sound(chicken);
```
```java
static void sound(Cat cat) {
		cat.sound();
	}
static void sound(Chicken chicken) {
		chicken.sound();
	}
```
- methodoverriding X : 타입을 확인하는 방식 (instanceof 사용)
```java
static void sound(Animal animal) {
		if(animal instanceof Cat) {
			((Cat)animal).sound();
		} else if(animal instanceof Chicken) {
			((Chicken)animal).sound();
		} else if (animal instanceof Dog) {
			((Dog)animal).sound();
		}
		
	}
```

**메서드 오버라이딩 method overrriding**
- 동일 선언 / 서로 다른 기능 구현
- 상속 관계 메서드 재정의 : 상속 관계에 있는 클래스에서 수퍼(상위)타입에 있는 메서드를 서브(하위)타입 클래스에서 재정의
- 상위 클래스 toString : 주소값 출력 -> 하위 클래스 toString : 객체 속성값 출력
- sound() 추가 : Animal 상속확장(extends)해서 Aniaml 클래스에 있는 sound() method override 구현 
```java
@Override
	void sound() {
//		super.sound(); // 상위 클래스의 기능을 사용
		System.out.println(">> 야옹 야옹");
	}
```
```java
sound(animal);
sound(cat);
```
```java
static void sound(Animal animal) {
		animal.sound();
	}
```

**Class**
- 구현체 : 모든 메서드를 구현
- 객체(인스턴스) 생성

**Interface**
- 추상체 : 메서드 선언부만 존재 (구현X)
- 단, default/static 구현 메서드가 있다.


**Abstract Class**
- 추상 클래스 : 구현 메서드와 추상 메서드가 함께 있는 클래스
- 직접 객체 생성(인스턴스화) 할 수 없고 반드시 추상 메서드가 구현되어야 한다.

-예제1
```java
abstract class AbstractAnimal { //abstract class에서만 abstract method 사용 가능

	String name; // 이름, 명칭
	int legCnt; // 다리 개수
	
	void eat() {
		System.out.println(">> 먹는다");
	}
	void sleep() {
		System.out.println(">> 잠을 잔다");
	}
	
	abstract void sound(); // 추상 메서드 (abstract method)
}
```
```java
class Cat extends AbstractAnimal {

	// 추상 클래스에서 선언된 메서드 반드시 구현
	@Override
	void sound() {
		System.out.println(">> 야옹");
	}

}
```
```java
		//Cannot instantiate the type AbstractAnimal
//		AbstractAnimal abstractAnimal = new AbstractAnimal();
		
		title("cat");
		Cat cat = new Cat();
		sound(cat);
```
- 예제2
```java
// 추상 메서드가 1개라도 있으면 클래스도 추상 클래스가 되어야 함
 abstract class AbstractAnimal implements Animal {

	@Override
	public void eat() {
		System.out.println(">> 먹는다");
		
	}

	@Override
	public void sleep() {
		System.out.println(">> 잠을 잔다");
		
	}

	@Override
	public abstract void sound(); // 추상 메서드

}
```
```java
public class Cat extends AbstractAnimal {

	@Override
	public void sound() {
		System.out.println(">> 야옹");
		
	}
}
```
```java
	title("Cat");
		Cat cat = new Cat();
		cat.eat();
		cat.sleep();
		cat.sound();
		cat.test();

		AbstractAnimal cat2 = new Cat(); //상위 타입 <- 하위 타입
		cat2.eat();
		cat2.sleep();
		cat2.sound();
//		cat2.test(); //정의되지 않은 메서드
		
		Animal cat3 = new Cat(); //인터페이스 <- 구현한 객체
		cat3.eat();
		cat3.sleep();
		cat3.sound();
//		cat3.test();
```
```java
//상위 클래스에 저장해서 사용(AbstractAnimal 타입으로 사용)
static void sound(AbstractAnimal animal) {
		animal.sound();
	}
// 인터페이스 타입으로 사용
	static void sound(Animal animal) {
		animal.sound();
	}
```

