# Java-study

# 실습. 문자열 다루기
String str = "900108-1234567"; //주민등록번호
1. 정확히 입력된 데이터 여부 확인 (전체 자리수 : 14, '-' 위치 : 7번째)
2. 성별 확인 후 출력 (1,3 : 남성 / 2,4 : 여성)
3. 생년월일 출력 (1-2번째: 년도, 3-4번째 : 월, 5-6번째 : 일)
4. 데이터 값 검증(월 : 1~12 / 일 : 1~31) 
- 참고 : int num = Interger.parseInt("12"); ("12"->12)

```java
	public static void main(String[] args) {
		
		String str = "900108-1234567";
		System.out.println("주민등록번호 : " + str);
		
		//1. 정확히 입력된 데이터 여부 확인 
		//(전체 자리수 : 14, '-' 위치 : 7번째)
		char[] ch = str.toCharArray();
		if (ch.length == 14) {
		} else {
			System.out.println();
			System.out.println(">> 14자 이상입니다. 다시 입력해주십시오.");
		}
		if ((str.indexOf("-")+1) == 7) {
		} else {
			System.out.println();
			System.out.println(">> '-'의 위치가 잘못되었습니다. 다시 입력해주십시오.");
		}
		
		//2. 성별 확인 후 출력 (1,3 : 남성 / 2,4 : 여성)
		int birth = Integer.parseInt(str.substring(0,2));
		
		if (str.charAt(7) == '1') {
			System.out.println("성별 : 남성");
			System.out.print("생년 : 19");
			System.out.println(birth);
		} else if (str.charAt(7) == '3') {
			System.out.println("성별 : 남성");
			if (22 < birth) {
				System.out.println("없는 년도입니다. 다시 입력해주십시오.");
			} else {
				System.out.print("생년 : 20");
				System.out.println(birth);
			}
		} else if (str.charAt(7) == '2') {
			System.out.println("성별 : 여성");
			System.out.print("생년 : 19");
			System.out.println(birth);
		}  else if (str.charAt(7) == '4') {
			System.out.println("성별 : 여성");
			if (22 < birth) {
				System.out.println("없는 년도입니다. 다시 입력해주십시오.");
			} else {
				System.out.print("생년 : 20");
				System.out.println(birth);
			}
		} else {
			System.out.println(">> 뒷자리 첫번째 숫자를 다시 입력해주십시오.");
		}
		
		//3. 생년월일 출력
		//(1-2번째: 년도, 3-4번째 : 월, 5-6번째 : 일)
		//4. 데이터 값 검증(월 : 1~12 / 일 : 1~31) 
		
		int month = Integer.parseInt(str.substring(2,4));
		int day = Integer.parseInt(str.substring(4,6));
		
		
		if (1 > month) {
			System.out.println(">> 없는 달입니다. 다시 입력해주십시오.");
		} else if (12 < month) {
			System.out.println(">> 없는 달입니다. 다시 입력해주십시오.");
		} else {
			System.out.println("월 : " + month);
		}
		
		if (1 > day) {
			System.out.println(">> 없는 일입니다. 다시 입력해주십시오.");
		} else if (31 < day) {
			System.out.println(">> 없는 일입니다. 다시 입력해주십시오.");
		} else {
			System.out.println("일 : " + day);
		}
	}
}
```
