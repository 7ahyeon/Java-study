# Scanner 사용 카페 전산 처리 실습

- 메뉴
1. 아메리카노	3000
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
	
	Scanner cafe = new Scanner(System.in);
	private String menu;
	private int num;
	private int inpay;
	private int outpay;
	private int backpay;
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
		System.out.println("메뉴 선택 (1-4) : ");
		menu = cafe.next();
	}
	
	private void input() {
		System.out.println("주문 수량 : ");
		num = cafe.nextInt();
		cafe.nextLine();
		
		System.out.println(" 입금액 : ");
		inpay = Integer.parseInt(cafe.nextLine());
	}
	
	private void process() {
			if (menu.equals("1")) {
				outpay = 3000 * num;
			} else if (menu.equals("2")) {
				outpay = 3500 * num;
			} else if (menu.equals("3")) {
				outpay = 4000 * num;
			} else if (menu.equals("4")) {
				outpay = 5000 * num; 
			} else if (!menu.equals("0")){
				System.out.println("----존재하지 않는 메뉴입니다.----");		
			}
			
			if (inpay >= outpay) {
			backpay = inpay - outpay;
			} else {
				System.out.println("----다시 입금해주십시오.----");
				systemAgain();
			}
	}
	
	private void output() {
		System.out.println("-----------------");
		System.out.println(" 입금액 : " + inpay);
		System.out.println(" 판매액 : " + outpay);
		System.out.println(" 잔액 : " + backpay);
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

```java

```
