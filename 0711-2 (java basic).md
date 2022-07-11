# 실습. 문자열 다루기 총정리
```java
주민등록번호 : 900116-1234567
성별 : 남성
생년월일 : 1990년 1월 16일
```
```java
	public static void main(String[] args) {
		/* String str = "900108-1234567"; //주민등록번호

	1. 정확히 입력된 데이터 여부 확인 (전체 자리수 : 14, '-' 위치 : 7번째)
	2. 성별 확인 후 출력 (1,3 : 남성 / 2,4 : 여성)
	3. 생년월일 출력 (1-2번째: 년도, 3-4번째 : 월, 5-6번째 : 일)
	4. 데이터 값 검증(월 : 1-12 / 일 : 1-31)
	참고 : int num = Interger.parseInt("12"); ("12"->12)
	*/
	
		String str = "900116-1234567";
		System.out.println("주민등록번호 : " + str);
		int strL = str.length();
		if (strL == 14) {
		} else {
			System.out.println("[비정상] 전체 자리수가 " + strL + "입니다.");
		}
		if (str.charAt(6) == '-') {
		} else {
			System.out.println("[비정상] 7번째 위치에 '-'가 존재하지 않습니다.");
		}
		
		String gender = str.substring(7, 8);
		switch (gender) {
		case "1" : case "3" :
			System.out.println("성별 : 남성");			
			break;
		case "2" : case "4" :
			System.out.println("성별 : 여성");
			break;
		default:
			System.out.println("[비정상] 뒷자리 첫번째 숫자가 잘못 입력되었습니다.");			
			break;
		}
		
		
		String yyyy = "";
		String yy = str.substring(0, 2);
		switch (gender) {
		case "1" : case "2" :
			yyyy = "19" + yy;
			System.out.print("생년월일 : " + yyyy + "년 ");
			break;
		case "3" : case "4" :
			yyyy = "20" + yy;
			System.out.print("생년월일 : " + yyyy + "년 ");
			break;
		default:
			System.out.println("[비정상] 뒷자리 첫번째 숫자가 잘못 입력되었습니다.");			
			break;
		}
		
		int mm = Integer.parseInt(str.substring(2, 4));
		if (mm >= 1 && mm <= 12) {
			System.out.print(mm + "월 ");
		} else {
			System.out.println();
			System.out.println("[비정상] 월 데이터(1-12)가 잘못 입력되었습니다.");
		}
		
		int dd = Integer.parseInt(str.substring(4, 6));
		if (dd >= 1 && dd <= 31) {
			System.out.println(dd + "일");
		} else {
			System.out.println("[비정상] 일 데이터(1-31)가 잘못 입력되었습니다.");
		}

	}

}
```
