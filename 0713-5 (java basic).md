# Java-study

**상속 inheritance**
- 기존의 클래스에 기능을 추가하거나 재정의하여 새로운 클래스를 정의하는 것을 의미
- 상위 클래스가 가지고 있는 속성(변수)들과 기능(메서드)들을 그대로 물려받아 새로운 클래스를 만드는 것.
   
**재활용성**
- 상위 클래스에 정의된 멤버필드(변수)나 메서드들을 그대로 상속받아 사용
- 상속받은 메서드라 해도 필요에 따라서 하위 클래스에서 용도를 변경해서 사용(method overriding)   
   
- 생성자, 초기화 블럭 : 상속 불가
- 상위 클래스의 접근제한자가 private인 경우 하위 클래스가 상속을 받았어도 접근 불가   
   
`
상위클래스 : 상속의 대상이 되는 클래스 (수퍼(super)클래스, 부모(parent)클래스, 기초/기반 클래스(Base class))
`
   
`
하위클래스 : 상속받아서 추가 확장 구현한 클래스 (서브(sub)클래스, 자녀(child)클래스, 파생 클래스(Derived class))   
`
   

**핵심 키워드**

1. **확장 extends**
- 동일한 타입간에 확장해서 사용할 때 사용
- extends문 좌우에 동일한 타입(class, interface)이 와야한다.
   
- class extends class : 클래스는 단일 상속만 허용 (in java)
- interface extends inteface1, interface2, ...interfaceN : 인터페이스는 다중 상속 허용
   
   
   
2. **실체화 / 구현 implements**
- 인터페이스(interface 추상체 : method가 선언만 되어있는 것)를 구현해서 사용할 때 사용 
- class implements interface (,interface, inteface...)

```java
//public class Phone extends Object {
	class Phone { //extends Object : 생략 가능(컴파일러 자동 작성)
	
		// field (속성) ---
		private String type; //폰 타입 (형태)
		private String phoneNo; //전화번호
		
		// 생성자 ---
		public Phone(String phoneNo) {
			this.type = "Phone 타입";
			this.phoneNo= phoneNo;
		}

		public Phone(String type, String phoneNo) {
			super();
			this.type = type;
			this.phoneNo = phoneNo;
		}

		// method ---

		public String getType() {
			return type;
		}

		public void setType(String type) {
			this.type = type;
		}

		public String getPhoneNo() {
			return phoneNo;
		}

		public void setPhoneNo(String phoneNo) {
			this.phoneNo = phoneNo;
		}
		
		//전화 걸기 기능
		public void call() {
			System.out.println(">> 전화 걸기 ~ ");
		}
		
		//전화 받기 기능
		public void receiveCall() {
			System.out.println(">> 전화 받기 ~ ");
		}
		
		//전화 정보 보기
		public void view() {
			System.out.println("타입 : " + type + ", " + "전화 번호 : " + phoneNo);
		}
```
```java
class Mp3Phone { //현재 패키지에서만 사용 가능
	private String type;
	private String phoneNo;
	
	public Mp3Phone(String phoneNo) {
		type = "Mp3Phone 타입";
		this.phoneNo = phoneNo;
	}

	public Mp3Phone(String type, String phoneNo) {
		super();
		this.type = type;
		this.phoneNo = phoneNo;
	}

	public String getType() {
		return type;
	}

	public String getPhoneNo() {
		return phoneNo;
	}
	
	//전화 걸기 기능
	public void call() {
		System.out.println(">> 전화 걸기 ! ");
	}
			
	//전화 받기 기능
	public void receiveCall() {
		System.out.println(">> 전화 받기 ! ");
	}
			
	//전화 정보 보기
	public void view() {
		System.out.println("타입 : " + type + ", " + "전화 번호 : " + phoneNo);
	}
	//음악 플레이 기능 -------
	public void playMusic() {
		System.out.println(">> 음악 플레이 ! ");
	}

	@Override
	public String toString() {
		return "Mp3Phone [type=" + type + ", phoneNo=" + phoneNo + "]";
	}

}

```
```java
public class PhoneTest {

	public static void main(String[] args) {
		// Phone 객체 생성 후 사용 
		System.out.println("---Phone---");

		Phone ph1 = new Phone("010-1111-1111");
		ph1.view();
		ph1.call();
		ph1.receiveCall();
		
		Phone ph2 = new Phone("se2", "010-2222-2222");
		ph2.view();
		ph2.call();
		ph2.receiveCall();
		String objString = ph2.toString(); //Object 클래스의 메서드 호출(실행)
		System.out.println("ph2.toString() : " + objString);
		
		System.out.println("\n---Mp3Phone---");
		Mp3Phone mp3ph = new Mp3Phone("010-3333-3333");
		mp3ph.view();
		mp3ph.call();
		mp3ph.receiveCall();
		mp3ph.playMusic();
		System.out.println(mp3ph.toString());
		
	}

}

```
```java
---Phone---
타입 : Phone 타입, 전화 번호 : 010-1111-1111
>> 전화 걸기 ~ 
>> 전화 받기 ~ 
타입 : se2, 전화 번호 : 010-2222-2222
>> 전화 걸기 ~ 
>> 전화 받기 ~ 
ph2.toString() : com.mystudy.ex01_class.Phone@7ca48474

---Mp3Phone---
타입 : Mp3Phone 타입, 전화 번호 : 010-3333-3333
>> 전화 걸기 ! 
>> 전화 받기 ! 
>> 음악 플레이 ! 
Mp3Phone [type=Mp3Phone 타입, phoneNo=010-3333-3333]
```















