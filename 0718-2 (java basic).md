
1. 에러(error) : 프로그램적으로 처리할 수 없음(JVM에서 처리)
2. 예외(Exception) : 프로그래머가 해결해야하는 오류

#Exception

**예외 Exception**
- 예외 중 최상 클래스 : java.lang.Throwable
- RuntimeException : 실행시 발생하는 Exception
- 그외 Exception : 컴파일 단계에서 확인가능한 Exception (예외 처리 필수)

**예외 처리**
- 프로그램 실행시 발생할 수 있는 예외에 대한 처리 코드를 작성하는 것
- 프로그램 실행시 비정상적인 종료를 막고, 정상 실행상태를 유지하기 위한 행위
- 예외 처리시 사용할 키워드 : try ~ catch, finally, throws, throw

**예외 처리 방식**
- catch 해서 처리 : 예외 발생시 예외에 대한 처리를 직접하는 것(이곳에서)
- 예외 던지기(throws) : 예외발생시 catch해서 처리하지 않고 던지는 것 (위임 : 호출한 곳에서 처리하도록 넘긴다)

**예외 발생**
- 인위적으로 예외를 발생시킴
- throw 예외명/예외타입;

**예외 생성**
- Exception 클래스를 상속받아서 예외를 정의하고 만들 수 있음

**예외 catch 처리**
- try ~ catch문 : try {  } catch(예외타입    변수명) {   }
- 예외 발생시 해당 예외를 catch한 곳에서 처리
  
- try ~ catch ~ finally문 : 
 ```java
 try {  
  	명령문들;
  } catch(예외타입    변수명) {   
         예외처리명령문들;  
  } finally {
         무조건 실행할 명령문들;  
  }
```
- finally{} : 비정상적/정상적 실행에 관련없이 무조건 실행되는 문장을 작성
  

**예외의 2종류**
1. RuntimeException 클래스 : 프로그래머의 실수로 발생하는 예외 (예외 처리 필수)
- ArithmeticException, ClassCastException, NullPointerException, IndexOutOfBoundsException...

2. Exception 클래스 : 사용자의 실수와 같은 외적인 요인에 의해 발생하는 예외 (선택적 처리)
- IOException, ClassNotFoundException...
  





