# 실습. String 사용

문자열 : "홍길동","이순신","이순신","을지문덕","김유신","연개소문","Tom","TOM"
		
1. 위의 문자열 값을 저장할 수 있는 문자열 배열(names) 변수를 선언하고 입력
2. 배열에 있는 값을 구분자 콤마(,)로 구분하여 한 라인에 출력
- 출력 예) 홍길동,이순신,이순신,을지문덕....
3. 배열에 있는 데이터의 첫 글자만 출력-구분자 콤마(,) 사용 한 라인에 출력
- 출력 예) 홍,이,이,을,김,연,T,T...
4. 이름의 글자수가 4글자 이상인 이름을 검색해서 "인덱스번호:이름" 형태로 출력
- 예) 3:을지문덕
5. 이름이 같은 데이터를 "인덱스번호:이름=인덱스번호:이름" 형태로 출력
- 예) 1:이순신=2:이순신
- (기타) 이름 비교시에는 대소문자 구분 없이 비교처리(Tom, TOM 은 같다)

```java
package com.mystudy.string;

public class Ex04_StringExam02 {
	

	public static void main(String[] args) {
		
		/* String 사용 실습
		문자열 : "홍길동","이순신","이순신","을지문덕","김유신","연개소문","Tom","TOM"
		
		1. 위의 문자열 값을 저장할 수 있는 문자열 배열(names) 변수를 선언하고 입력
		2. 배열에 있는 값을 구분자 콤마(,)로 구분하여 한 라인에 출력
		   출력 예) 홍길동,이순신,이순신,을지문덕....
		3. 배열에 있는 데이터의 첫 글자만 출력-구분자 콤마(,) 사용 한 라인에 출력
		   출력 예) 홍,이,이,을,김,연,T,T...
		4. 이름의 글자수가 4글자 이상인 이름을 검색해서 "인덱스번호:이름" 형태로 출력
		   예) 3:을지문덕
		5. 이름이 같은 데이터를 "인덱스번호:이름=인덱스번호:이름" 형태로 출력
		   예) 1:이순신=2:이순신
		(기타) 이름 비교시에는 대소문자 구분 없이 비교처리(Tom, TOM 은 같다)
		========================================================= */

//		1. 위의 문자열 값을 저장할 수 있는 문자열 배열(names) 변수를 선언하고 입력
		String[] names = new String[]{"홍길동","이순신","이순신","을지문덕","김유신","연개소문","Tom","TOM"};

//		2. 배열에 있는 값을 구분자 콤마(,)로 구분하여 한 라인에 출력
		print("names 배열 데이터 출력");
		
		for (int i = 0; i < names.length; i++) {
			if (i != (names.length-1)) {
				System.out.print(names[i] + ", ");
			} else {
				System.out.print(names[i]);				
			}
		}
		
		System.out.println();	
		
//		3. 배열에 있는 데이터의 첫 글자만 출력-구분자 콤마(,) 사용 한 라인에 출력
		print("배열 데이터 첫 글자만 출력");
		
		for (int i = 0; i < names.length; i++) {
			if (i != (names.length-1)) {
				System.out.print(names[i].substring(0, 1) + ", ");
			} else {
				System.out.print(names[i].substring(0, 1));
			}
		}	
		System.out.println();
		
//		4. 이름의 글자수가 4글자 이상인 이름을 검색해서 "인덱스번호:이름" 형태로 출력
		print("4글자 이상인 이름 출력");
		
		for (int i = 0; i < names.length; i++) {
			if (names[i].length() >= 4) {
				System.out.print(i + ": " + names[i] + " ");
			} else {}
		}
		System.out.println();
			
//		5. 이름이 같은 데이터를 "인덱스번호:이름=인덱스번호:이름" 형태로 출력
		print("이름이 같은 데이터 출력");
		
		for (int i = 0; i < names.length; i++) {
			for (int k = i; k < names.length; k++ ){
				if (names[i].equalsIgnoreCase(names[k]) && (i != k)) {
					System.out.println(i + ": " + names[i] + " = " + k + ": " + names[k]);
				}
			}
			
		}
		
	}
	static void print(String w) {
		System.out.println("-----" + w + "-----");
	}	
}

```
