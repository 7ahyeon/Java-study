# Java-study




**기계어 machine language** 컴퓨터(운영체제 OS)가 이해하고 실행할 수 있는 0과 1로 이루어진 이진 코드

**프로그래밍 언어** 사람과 기계어의 다리 역할 (ex: C, C++, Java, Python)

**소스 파일 source** 프로그래밍 언어로 작성된 파일

**컴파일 compile** 소스 파일을 기계어로 번역

**컴파일러 compiler** 컴파일을 담당하는 SW

**객체 지향 프로그래밍 OOP** 객체(부품)를 만들고 서로 연결해 더 큰 프로그램을 완성하는 기법 (Object-Oriented Programming)

**Java** 1. 객체 지향 프로그래밍을 위한 최적의 언어
         2. 메모리(RAM) 자동 관리 및 정리
         3. 무료 오픈 소스 라이브러리 풍부 (개발시간 단축)
         C:\Program Files\java\bin\javac.exe
                                    java.exe
         
**Java SE** 주 버전. 개선 버전. 업데이트 버전 (LTS)
         
**LTS** 장기 지원 서비스 (Long Term Support) (ex: Oracle)

**JDK** 자바로 프로그램을 개발할 수 있는 실행 환경 JVM(Java Virtual Machine)과 라이브러리 API, 개발 도구(ex: compiler) 포함된 SW Package (Java Development Kit)

**JRE** 자바 프로그램 실행에 필요한 JVM, 라이브러리 API가 포함된 SW Package (JDK(JRE(JVM)))


**환경 변수** 운영체제가 실행하는 데 필요한 정보를 제공해주는 변수
             명령라인(명령 프롬프트 cmd, 터미널)에서 컴파일러(javac)와 실행(java) 명령어 사용시 JAVA_HOME 환경 변수 등록/Path 환경 변수 수정 권장
             -> bin 폴더 내 위치하므로 다른 폴더에서 실행 불가하기 때문
         
**javac 명령어** 자바 소스 파일을 컴파일

**java 명령어** 컴파일된 파일을 실행

**JAVA_HOME** JDK가 설치된 폴더 (C:\Program Files\Java\jdk1.8.0_333)
             
**환경 변수 등록** 설정-디스플레이-정보-[고급 시스템 설정]-[환경 변수]-시스템 변수[새로 만들기]
                  변수 이름 'JAVA_HOME' 변수 값 'C:\Program Files\Java\jdk1.8.0_333)-[확인]
                  
**환경 변수 수정** 설정-디스플레이-정보-[고급 시스템 설정]-[환경 변수]-시스템 변수-Path[편집]
                  [새로 만들기]-'%JAVA_HOME%\bin'-[위로 이동]-[확인]
                  -> 다른 경로에서 bin 폴더 안에 있는 명령어를 사용할 수 있게 함
                  
**%JAVA_HOME%** JAVA_HOME의 환경 변수 값을 사용한다는 의미
                JAVA_HOME = C:\Program Files\Java\jdk1.8.0_333
                %JAVA_HOME%\bin = C:\Program Files\Java\jdk1.8.0_333\bin
                
**환경 변수 설정 확인법** cmd에서 javac -version 입력

             
## JAVA8u333/ORACLE2020-12 사용
