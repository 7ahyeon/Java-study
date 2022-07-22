# Scanner 사용 카페 전산 처리 실습

- 메뉴
1. 아메리카노 3000
2. 카페라떼 3500
3. 카페모카 4000
4. 과일주스 5000

- 입력 : 메뉴 번호, 주문 수량, 입금액 (고객이 낸 돈)
- 처리 : 입금액, 판매액 (단가 * 수량), 잔액 (입금액 - 판매액)
- 출력 : 입금액, 판매액, 잔액

|<메뉴>|1. 아메리카노 2. 카페라떼 3. 카페모카 4. 과일주스|
|:---:|:---:|
|메뉴 선택 (1-4)|1|
|주문 수량|3|
|입금액|10000|
|판매액|9000|
|잔액|1000|

```java
public class ScannerCafe {

private final int AMERICANO = 3000;
private final int CAFE_LATTE = 3500;
private final int CAFE_MOCA = 4000;
private final int FRUIT_JUICE = 5000;


Scanner cafe = new Scanner(System.in);
private String menu;
private int count; //수량
private int inMoney; //입금액
private int income; //판매금액(매출)
private int change; //거스름돈(잔액)
private String again;

public void system() {

	while (true) {			
		choice();
		if (menu.equals("0")) {
			System.out.println("---주문을 종료합니다---");
			break;
		} else {
			input();
			process();
			output();
			roof();
			break;
		}
	}
}
public void systemAgain() {
	while (true) {			
		choice();
		if (menu.equals("0")) {
			System.out.println("---주문을 종료합니다---");
			break;
		} else {
			input();
			process();
			break;
		}
	}
}

private void choice() {
	System.out.println("<메뉴>\r\n"
			+ " 1. 아메리카노 2. 카페라떼 3. 카페모카 4. 과일주스 0. 종료");
	System.out.print("메뉴 선택 (1-4) : ");
	menu = cafe.next();
}

private void input() {
	System.out.print("주문 수량 : ");
	count = cafe.nextInt();
	cafe.nextLine();

	System.out.print("입금액 : ");
	inMoney = Integer.parseInt(cafe.nextLine());
}

private void process() {
		if (menu.equals("1")) {
			income = AMERICANO * count;
		} else if (menu.equals("2")) {
			income = CAFE_LATTE * count;
		} else if (menu.equals("3")) {
			income = CAFE_MOCA * count;
		} else if (menu.equals("4")) {
			income = FRUIT_JUICE * count; 
		} else if (!menu.equals("0")){
			System.out.println("----존재하지 않는 메뉴입니다.----");		
		}

		if (inMoney >= income) {
		change = inMoney - income;
		} else {
			System.out.println("----다시 입금해주십시오.----");
			systemAgain();
		}
}

private void output() {
	System.out.println("-----------------");
	System.out.println("입금액 : " + inMoney);
	System.out.println("판매액 : " + income);
	System.out.println("잔액 : " + change);
	System.out.println("----주문을 종료합니다.----");

}

private void roof() {
	System.out.println("<재주문>\r\n"
			+ " 1. 재주문 0. 종료  : ");
	again = cafe.next();

	if (again.equals("1")) {
		system();
	} else if (again.equals("0")) {
		System.out.println("----주문을 종료합니다.----");
	} else {
		System.out.println("----다시 선택해주십시오.----");	
		roof();
	}
}
}

```

```java
public class ScannerCafeMain {
	public static void main(String[] args) {
		
		new ScannerCafe().system();
	
	}
}

```

