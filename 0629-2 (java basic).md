# Java-study

**자바 프로그램 개발 과정**

                           자바 소스 파일(.java)

                           -> javac 명령어 실행(compile)
                          
                          바이트 코드 파일(.class)
                          
                          -> java 명령어 실행
                          
                          JVM : 기계어 번역 후 실행

**인터프리터** 프로그래밍 언어의 소스 코드를 바로 실행하는 프로그램 또는 환경 (interpreter) <-> 컴파일러

**메소드 method** 어떤 일을 처리하는 실행문들을 모아 놓은 블록

**클래스 class** 객체를 생성하기 위한 필드와 메소드가 정의된 것 (객체의 설계도)

**실행문** 변수 선언, 값 저장, 메소드 호출에 해당하는 코드 (실행문 끝에는 세미콜론(;)이 필수)

**클래스 선언** 클래스 선언부 (클래스 이름 Hello) {클래스 블록}

`public class Hello {
    }`
    
**메소드 선언** 메소드 선언부 (메소드 이름 main)(String[] args){메소드 블록}

`public static void main(String[] args){
  System.out.println("Hello, Java")
  }`

**프로그램 실행 진입점** main() 메소드 

**메소드 호출** 메소드를 코드 내에서 사용하는 것

**주석 comment** 프로그램 실행과는 상관없이 코드에 설명을 붙인 것 ("문자열" 내부 이외 전부 가능)
                 1. // : 주석 부호부터 라인 전체
                 2. /*~*/ : 주석 부호 사이의 모든 범위
                 
**모니터에 출력하는 메소드 호출**  `System.out.println("출력하고 싶은 것");`

**저장 폴더** 소스파일(.java): src / 바이트 코드 파일(.class): bin

**문자열과 숫자**

`System.out.println("123456" + 1); //1234561`

`System.out.println(1 + "123456"); //1123456`

`System.out.println(12345 + 67890); //80235` 

**System.out.println()** sysout + Ctrl + Space

`	/* 화면에 구구단 2단 출력
		 2 * 1 = 2 // 2 * 1 출력값
		 2 * 2 = 4
		 ...
		 2 * 9 = 18
		 */
		
		System.out.println("2 * 1 = " + 2 * 1);
		System.out.println("2 * 2 = " + 2 * 2);
		System.out.println("2 * 3 = " + 2 * 3);
		System.out.println("2 * 4 = " + 2 * 4);
		System.out.println("2 * 5 = " + 2 * 5);
		System.out.println("2 * 6 = " + 2 * 6);
		System.out.println("2 * 7 = " + 2 * 7);
		System.out.println("2 * 8 = " + 2 * 8);
		System.out.println("2 * 9 = " + 2 * 9);`
		

