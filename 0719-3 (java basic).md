# Generic

**Generic**
- 컬렉션이 어떤 객체들로 이루어졌는지 표시하는 객체타입을 의미
- 제네릭 형태 : <객체자료형>, <>
- API -> <T> : 객체자료형, <E> : 하나의 요소(즉 객체 하나를 의미)
- Map형식 : <K, V> K는 key(키), V는 value(값)

```java
class Box {
	Object obj; //필드(멤버) 변수의 타입
	public Object getObj() {
		return obj;
	}
	public void setObj(Object obj) {
		this.obj = obj;
	}
}
```
```java
//제네릭 적용된 박스
class BoxG<T> {
	T obj;
	T getObj() {
		return obj;
	}
	void setObj(T obj) {
		this.obj = obj;
	}
}
```
```java
Box box = new Box();
		box.setObj("문자열 String");
		box.setObj(100);
		box.setObj(new Box());
		box.setObj(new Integer(999));
		System.out.println(box.getObj());
		
		Integer integer = (Integer)box.getObj();
		System.out.println("Integer : " + integer);
```
```java
	System.out.println("---Generic 적용---");
		BoxG<String> boxg = new BoxG<String>();
		boxg.setObj("문자열 String");
		
		String str = "World";
		int str2 = 333;
		
		boxg.setObj(str);
//		boxg.setObj(str2); // 타입이 맞지 않으면 컴파일 오류 발생

		System.out.println(boxg.getObj());
		String strReturn = boxg.getObj();

		System.out.println("------");
		BoxG<Integer> boxg2 = new BoxG<Integer>();
		boxg2.setObj(100);

//		boxg2.setObj(str); // 타입이 맞지 않으면 컴파일 오류 발생
		boxg2.setObj(str2);
		
		System.out.println(boxg2.getObj());
		Integer intReturn = boxg2.getObj();
```

**대표문자 wildcard**
1. <?> : 모든 타입(객체) 자료형에 대한 대표문자를 의미
2. <? extends 자료형> : 자료형을 상속받은 하위(sub) 클래스 타입 사용
3. <? super 자료형> : 자료형의 상위(super) 타입 사용           

```java
//		 Wild card 

//		1. <?> : 모든 타입(객체) 자료형에 대한 대표문자를 의미
		BoxT<?> box = new BoxT<String>();
		box = new BoxT<Integer>();
		box = new BoxT<StringBuilder>();
		
//		2. <? extends 자료형> : 자료형을 상속받은 하위(sub) 클래스 타입 사용
		BoxT<? extends Number> box2 = new BoxT<Number>();
		box2 = new BoxT<Byte>();
		box2 = new BoxT<Integer>();
		box2 = new BoxT<Double>();
//		box2 = new BoxT<Object>();  // 오류
//		box2 = new BoxT<String>();  // 오류
		
//		3. <? super 자료형> : 자료형의 상위(super) 타입 사용  
		BoxT<? super Number> box3 = new BoxT<Number>();
		box3 = new BoxT<Object>();
		box3 = new BoxT<Number>();
//		box3 = new BoxT<Integer>(); // 오류
```





