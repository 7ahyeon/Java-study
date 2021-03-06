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
	
	//기본 생성자 default constructor
	public Student() {
		//super : 부모(조상) 클래스로 만들어진 객체(인스턴스)
		//super() : 부모 클래스의 기본 생성자 호출
		//부모 클래스 생성자 호출은 생성자의 맨 처음에 작성되어야 함
		super();//생략시 컴파일 과정에서 자동 삽입되어 처리됨
	}
	
	//source -> constructor using fields
	public Student(String name) { //타입 (생성자)
	super(); // 부모 클래스 타입 (첫 줄에 작성/생략 가능)
	this.name = name;
	}
	
	// 외부에서 접근(사용) 가능하도록 method 제공(public)
	// 명칭 : set method, setter, set property
	//source -> setters getters
	public void setName(String name) {
		this.name = name;
	}
	
	// 명칭 : get method, getter, get property
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
**실습**
```java
private int kor;
private int eng;
private int math;
private int tot;
private double avg;
public Student(String name, int kor, int eng, int math) {
	//this :부모 클래스로 인해 만들어진 현재 객체
	this(name); //생성자 호출 코드 첫번째 실행 코드 
//	this.name = name;
	this.kor = kor;
	this.eng = eng;
	this.math = math;
	computeTotAvg();
	
// kor set method
public void setKor(int kor) {
	if(kor >= 0 && kor <= 100) {
		this.kor = kor;
		computeTotAvg();
		} else {
			System.out.println("[예외] 0-100 범위가 아님");
		}
}
// kor get method
public int getKor() {
	return kor;
}
	
public void setEng(int eng) {
	if (eng >= 0 && eng <= 100) {
		this.eng = eng;
	} else {
		System.out.println("[오류] 1-100의 범위를 벗어났습니다.");
	}
}
		
	
public int getEng() {
	return eng;
}
	
public void setMath(int math) {
	if (math >= 0 && math <= 100) {
		this.math = math;
	} else {
		System.out.println("[오류] 1-100의 범위를 벗어났습니다.");
	}
}
	
public int getMath() {
	return math;
}
	
	
public void setTot() {
	int tot = kor + eng + math;
	this.tot = tot;
}
	
public int getTot() {
	return tot;
}
	
public void setAvg() {
	double avg = (double)(tot * 100 / 3 / 100.0) ;
	this.avg = avg;
}
	
public double getAvg() {
	return avg;
}

public void computeTotAvg() {
	tot = kor  + eng + math;
	avg = tot * 100 / 3 / 100.0;
}
//source -> toString()
@Override
public String toString() {
	return "Student [name=" + name + ", kor=" + kor + ", eng=" + eng + ", math=" + math + ", tot=" + tot + ", avg="
				+ avg + "]";
}
	
```
```java
stu.setKor(100);
System.out.println("kor : " + stu.getKor());
		
stu.setEng(90);
System.out.println("eng : " + stu.getEng());
		
stu.setMath(70);
System.out.println("math : " + stu.getMath());
		
stu.setTot();
System.out.println("tot : " + stu.getTot());
		
stu.setAvg();
System.out.println("avg : " + stu.getAvg());

System.out.println(stu);

Student stu2 = new Student("자바2", 80, 70, 65);
System.out.println(stu2);
```	
		





