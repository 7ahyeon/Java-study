# Java-study

**상수 constant** 값이 변하지 않음

**변수 variable** 
- 값이 변함
- 값data을 저장할 수 있는 메모리의 공간 (.참조 표시)

**예약어 reserved word/keyword** 
- 이미 해당 프로그래밍 언어에서 사용하기 위해 의미가 정해져 있는 것
- 변수로 사용 불가

**데이터 data**
- 문자(열) : 기본(문자형)(참조)
- 숫자 : 기본(실수형/정수형)
- 날짜 : 참조

**타입 type** 데이터 저장 형식

**기본 타입 primitive type** 8개
- **논리형** boolean (true/false)
- **문자형** char (2byte)(문자 1글자 저장(65536개))
- **실수형** float (4byte), **double (8byte)** (소수점 이하 존재)
- **정수형** byte (1byte), short (2byte), **int (4byte)**, long (8byte)

**참조 타입 reference type** 무한히 많음 **문자열/날짜**

**변수 선언** 어떤 타입의 데이터를 저장할 것인지 식별자(이름)는 무엇인지 결정

- `int x;
int y;
int z;`

- `int x,y,z;`

- 같은 타입의 변수는 콤마(,)를 이용해 한번에 선언 가능

**초기화 initialize** 변수에 초기값을 주는 행위

**초기값 initial value** 변수를 선언하고 처음 저장하는 값

**int 변수 = 초기값** 선언과 동시에 값 지정 가능

**bit** 0,1

**byte** 1byte = 8bit (ex:00001111) 
- 2^8 = 256개 (0~255)
- 8진수로 사용되는중

**문자형 char** 2byte = 16bit 
- 2^16 = 65536개 (0~65535)
- 문자(리터럴 literal) : 작은 따옴표 ('')
- (ex : 'A'=문자, "A"=문자열, 'AB'=사용 불가 )

`char c1 = 'A';`
`char c2 = 65;`
`char c3 = '\u0041';`

**문자열 String** 큰 따옴표 ("")

**문자열+문자+숫자** = 문자열 문자 숫자
- char1 : A1
`System.out.println("char1 : " + char1+1);`

**문자+숫자** = 숫자
- 66
`System.out.println(char1+1);`

**문자열+숫자** = 문자열 숫자
- char1 : 1
`System.out.println("char1 : "+1);`


**문자열+(문자+숫자)** = 문자열 숫자
- char1 : 66
`System.out.println("char1 : " + (char1+1));`

**형변환**
- **(int)변수** 변수의 정수값
- **(char)변수** 변수를 문자로

`System.out.println("char1 : " + char1);`
- char1 : A

`System.out.println("char1 정수값 : " + (int)char1);`
- char1 정수값 : 65

`System.out.println("char1 다음 문자 : " + (char)(char1 + 1));`
- char1 다음 문자 : B
		
**아스키 ASCII**  7bit로 표현되는 영문자 기반 인코딩 (유니코드 앞부분에 할당되어있음)
- 10 : LF(Line Feed ; 다음 줄로) / 13 : CR (Cariage return ; 제일 처음 칸으로)
- 10과 13은 줄바꿈시 사용

**이진법 Binary** bin파일 : 컴퓨터가 사용하는 이진 텍스트 파일

**UTF-8** 1byte, 3byte 등 유동적으로 사용

**UTF-16** 2byte만 사용

**유니코드 unicode** 세계 각국의 문자를 2byte로 표현할 수 있는 숫자(0~65535)로 매핑한 국제 표준 규약
- **\uHEX :** 유니코드 (ex: \uAC00 = 가)
- **HEX :** 16진수 표기법



