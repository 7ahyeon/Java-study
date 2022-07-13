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


