# String, StringBuffer, StringBuilder

**String**
- 불변 (immutable) (조회 연산에 유리)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 부적합
- thread-safe : 멀티 스레드 환경에서의 안정성
- 문자열 연산이 적고 조회가 많은 멀티 쓰레드일 경우

**StringBuffer**
- 가변 (mutable)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 적합
- thread-safe O: 멀티 스레드 환경에서의 안정성 (동기화Synchronized 키워드Keyword 제공)
- 문자열 연산이 많고 멀티 스레드일 경우 (스레드에 안전한 프로그램이 필요할 때)

**StringBuilder**
- 가변 (mutable)
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

# Wrapper class : 

**Wrapper class**
- 기본 데이터 타입primitive type의 기능 확장한 클래스 통칭

- 기본 데이터 타입 : 전체 소문자
- ex) boolean, char, byte, short, int, long, float,double
		
- Wrapper class : 기본 데이터 타입의 첫 글자를 대문자로 
- ( 예외 : char -> Character, int -> Integer)
- ex) Boolean, Character, Byte, Short, Integer, Long, Float,Double


