# 실습. 문자열 다루기
String str = "900108-1234567"; //주민등록번호
1. 정확히 입력된 데이터 여부 확인 (전체 자리수 : 14, '-' 위치 : 7번째)
2. 성별 확인 후 출력 (1,3 : 남성 / 2,4 : 여성)
3. 생년월일 출력 (1-2번째: 년도, 3-4번째 : 월, 5-6번째 : 일)
4. 데이터 값 검증(월 : 1-12 / 일 : 1-31) 
- 참고 : int num = Interger.parseInt("12"); ("12"->12)

```java

package com.mystudy.string;

public class Ex03_StringExam2 {

	public static void main(String[] args) {
		
		String str = "900717-1234567";
		
		//1. 정확히 입력된 데이터 여부 확인 
		//(전체 자리수 : 14, '-' 위치 : 7번째)
		
		print("전체 데이터 크기 확인");
		int strLen = str.length();
		if (strLen == 14) {
			System.out.println("[정상] 전체 길이 14자리");
			} else {
				System.out.println("[비정상] 전체 길이" + strLen);
			}
		
		// 7번째 문자(idx6) '-' 여부 확인
		System.out.println(">> str.charAt(6) 사용");
		print("7번째 문자(-) 확인");
		if (str.charAt(6) == '-') {
			System.out.println("[정상] 7번째 위치에 '-'가 존재합니다.");
		} else {
			System.out.println("[비정상] 7번째 위치에 '-'가 존재하지 않습니다.");			
		}
		
		// '-'문자의 위치를 확인 (첫번째로 찾은 '-'의 위치 idx6 여부)
		System.out.println(">> str.indexOf('-') 사용 (비정상일 때만 처리)");
		if (str.indexOf('-') != 6) {
			System.out.println("[비정상] '-'가 7번째 위치에 존재하지 않습니다. : " + str.indexOf('-'));			
		} 
		
		print("문자열 비교 처리 : equals() 사용 할 것");
		System.out.println(">> substring() 사용");
		System.out.println("\"-\".equals(str.substring(6, 7)) : " + "-".equals(str.substring(6, 7)));
//		if (str.substring(6, 7) == ("-")) // 정상 처리X
//		if (str.substring(6, 7).equals("-")) { //str = null일 경우 정상 처리X
		if ("-".equals(str.substring(6, 7))) {
			System.out.println("[정상] 6번째 인덱스에 \"-\"가 존재합니다.");
		} else {
			System.out.println("[비정상] 6번째 인덱스에 \"-\"가 존재하지 않습니다.");
		}
		
		print("");
//		2. 생년월일 출력 (1-2번째: 년도, 3-4번째 : 월, 5-6번째 : 일)
		String yymmdd = str.substring(0, 6);
		System.out.println("yymmdd : " + yymmdd);
		String yy = yymmdd.substring(0, 2);
		String mm = yymmdd.substring(2, 4);
		String dd = yymmdd.substring(4, 6);
		System.out.println("생년월일 : " + yy + "년 " + mm + "월 " + dd + "일");
		
		String flag = str.substring(7, 8);
		String yyyy = yy;
		if ("1".equals(flag) || "2".equals(flag)) {
			yyyy = "19" + yy;
		} else if ("3".equals(flag) || "4".equals(flag)) {
			yyyy = "20" + yy;
			} else {
				yyyy = "오류";
			}
		System.out.println("생년월일 : " + yyyy + "년 " + mm + "월 " + dd + "일");
		print("");
		
		switch (flag) {
		case "1" :
		case "2" :
			yyyy = "19" + yy;
			break;
		case "3" : case "4" :
			yyyy = "20" + yy;
		default :
			yyyy = yy;
			break;
		}
		System.out.println("생년월일 : " + yyyy + "년 " + mm + "월 " + dd + "일");
		print("");

//		3. 성별 확인 후 출력 (1,3 : 남성 / 2,4 : 여성)
		
		print("성별 확인 후 성별 표시");
		String gender = str.substring(7, 8);
		if ("1".equals(gender) || "3".equals(gender)) {
			System.out.println("주민등록번호 뒷자리(첫글자) :" + gender + " (남성)");
		} else if ("2".equals(gender) || "4".equals(gender)) {
			System.out.println("주민등록번호 뒷자리(첫글자) :" + gender + " (여성)");
		}
		
		print("");
		switch (gender) {
		case "1" : case "3" :
			System.out.println("주민등록번호 뒷자리(첫글자) :" + gender + " (남성)");
			break;
		case "2" : case "4" :
			System.out.println("주민등록번호 뒷자리(첫글자) :" + gender + " (여성)");
			break;
		default :
			System.out.println("외국인이나 잘못 입력되었습니다.");
			break;
		}
		
//		4. 데이터 값 검증(월 : 1~12 / 일 : 1~31) 
		
		print("월(1-12), 일(1-31) 값 검증");
		
		int month = Integer.parseInt(mm); //int<-String 형변환 
		if (month >= 1 && month <= 12) {
			System.out.println("[정상] 월 데이터 (1-12)");
		} //비정상에 대한 처리만 할 경우 (else 사용도 ok)
		if (month < 1 || month > 12) {
			System.out.println("[비정상] 월 데이터가 범위(1-12)를 벗어났습니다. (데이터 : " + month + ")");			
		}
		
		System.out.println(">> 일자 확인");
		int day = Integer.parseInt(dd);
		if (day >= 1 && day <= 31) {
			System.out.println("[정상] 일 데이터 (1-31)");
		} if (day < 1 || day > 31) {
			System.out.println("[비정상] 일 데이터가 범위(1-31)를 벗어났습니다. (데이터 : " + day + ")");				
		}
	}
	
	static void print(String w) {
		System.out.println("-----" + w + "-----");}

}
```
