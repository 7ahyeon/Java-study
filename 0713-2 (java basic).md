# Java Bean

**캡슐화 Encapsulation**
- 정보 은닉 (Information Hiding)
- 주로 속성은 숨기고 속성에 접근시 기능(method)를 통해 접근 처리

**자바 빈 Java Bean**
- 데이터를 저장하고 접근을 제어하여 데이터를 관리하는 클래스
- 특정 정보를 가지고 있는 클래스를 표현하는 하나의 규칙
- 데이터를 저장 · 조회시 기능(method)를 통해서 접근하게 만들어둔 것

- 멤버 변수(property)의 접근 제한자(제어자) : private으로 선언
- 멤버 변수(property)마다 get/set method(public으로 선언) 제공 (선택적으로 get만 제공) 
- set method : 하나 이상의 파라미터 O · 데이터 쓰기(설정)
- get method : 파라미터 X · 데이터 읽기
- 멤버 변수(property)가 boolean 타입이면 get 대신 is method 사용 가능

- 외부에서 멤버 변수(property) 접근시에는 get/set method 통해 접근

```java
public class Student { //public유무로 외부 접근 허용 유무가 결정됨
	private String name; //private 선언시 클래스 내에서만 사용 가능 (외부 접근 불가)
	private int kor;
	private int eng;
	private int math;
	private int tot;
	private double avg;
	
	// 외부에서 접근(사용) 가능하도록 method 제공(public)
	// 명칭 : set method, setter, set property
	public void setName(String name) {
		this.name = name;
	}
	
	public String getName() {
		return name;
	}
	```
  ```java
  	public static void main(String[] args) {
		
		Student stu = new Student();
//		stu.name = "자바";
//		System.out.println(stu.name);
			
		stu.setName("자바");
		System.out.println("name : " + stu.getName());
	}
}
```








