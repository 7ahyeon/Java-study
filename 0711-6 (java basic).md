# String, StringBuffer, StringBuilder

**String**
- 불변 (immutable) (조회 연산에 유리)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 부적합
- thread-safe : 멀티 스레드 환경에서의 안정성
- 문자열 연산이 적고 조회가 많은 멀티 쓰레드일 경우

**StringBuffer**
- 가변 (mutable) : append 가능
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 적합
- thread-safe O: 멀티 스레드 환경에서의 안정성 (동기화Synchronized 키워드Keyword 제공 : dead-lock 위험성 존재)
- 문자열 연산이 많고 멀티 스레드일 경우 (스레드에 안전한 프로그램이 필요할 때 )

**StringBuilder**
- 가변 (mutable) : append 가능
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 적합
- 단일 쓰레드 환경에서의 성능 뛰어남
- thread-safe X : 멀티 스레드 환경 부적합 (동기화 키워드 제공X)
- 문자열 연산이 많고 단일single 스레드거나 동기화를 고려하지 않아도 되는 경우 (스레드에 프로그램 안전 여부 관련X)

||String|StringBuffer|StringBuilder|
|:---:|:---:|:---:|:---:|
|Storage|String pool|Heap|Heap|
|Modifiable|X (immutable)|O (mutable)|O (mutable)|
|Thread-safe|O(multi)|O(multi)|X(single)|
|Synchronized|O|O|X|
|Performance|Fast|Slow|Fast|

**멀티 스레드 multi thread**
- 가변 객체는 동시 접근이 가능하여 안전하지 않음

**동기화 Synchronized**
- 한 스레드가 진행중인 작업을 다른 스레드가 간섭하지 못하게 막는 것
- 문자열 연산 시행 : 메모리 공간에서 직접 저장된 값을 변경 X -> 새로 인스턴스 생성 후 주소값을 저장 O



# Wrapper class : 

**Wrapper class**
- 기본 데이터 타입primitive type의 기능 확장한 클래스 통칭

- 기본 데이터 타입 : 전체 소문자
- ex) boolean, char, byte, short, int, long, float,double
		
- Wrapper class : 기본 데이터 타입의 첫 글자를 대문자로 
- ( 예외 : char -> Character, int -> Integer)
- ex) Boolean, Character, Byte, Short, Integer, Long, Float,Double

**Integer**
- String <- Integer : X
- Integer <-String : O (Integer.valueOf("String"))
- int <- String : O (Integer.parseInt("String"))
- Integer <-> int : O (자동 형변환)


```java
int num = 100;
//num = "100"; //Type mismatch : cannot convert from String to int
System.out.println("num : " + num);
		
Integer numInteger = new Integer(100);
//numInteger = "100"; //Type mismatch : cannot convert from String to Integer
System.out.println("numInteger : " + numInteger);

numInteger = 900; //Integer <- int : 자동 형변환
num = numInteger; //Integer -> int : 자동 형변환
		
System.out.println("num : " + num); //900
System.out.println("numInteger : " + numInteger); //900
```
```java
num = Integer.parseInt("999"); //int <- String
numInteger = Integer.valueOf("888"); // Integer <- String
```
```java
System.out.println("정수형 int 최대값 : " + Integer.MAX_VALUE); //2147483647
System.out.println("정수형 int 최소값 : " + Integer.MIN_VALUE); //-2147483648
```
