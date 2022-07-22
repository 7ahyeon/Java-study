# Scanner 사용 카페 전산 처리 실습 해답

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
public class Cafe {
	private Scanner scan = new Scanner(System.in);
	private final int AMERICANO = 3000;
	private final int CAFE_LATTE = 3500;
	private final int CAFE_MOCA = 4000;
	private final int JUICE = 5000;
	
	private int select; //메뉴선택 값
	private int count; //수량
	private int inMoney; //입금액
	private int income; //판매금액(매출)
	private int change; //거스름돈(잔액)
	
	private int totalIncome; //총판매액
	
	public void open() {
		while (true) {
			displayMenu();
			
			//메뉴선택
			selectMenu();
			
			if (select == 0) {
				System.out.println(">>>> 영업을 종료합니다~~");
				System.out.println(":::: 오늘 판매총액 : " + totalIncome);
				break;
			}
			
			System.out.print("> 주문수량(개) : ");
			count = scan.nextInt();
			
			System.out.print("> 입금액(원) : ");
			inMoney = scan.nextInt();
			
			//판매액계산 : 단가 * 주문수량
			computeIncome();
			
			
			//잔액(거스름돈) 계산 : 고객이 낸돈 - 판매액
			change = inMoney - income;
			
			//--------------------------
			//결과출력 : 입금액, 판매액, 거스름돈
			displayResult();
		}
	}

	private void selectMenu() {
		while (true) {
			try {
				System.out.print("메뉴를 선택하세요(1~4) : ");
				select = Integer.parseInt(scan.nextLine());
				break;
			} catch (Exception e) {
				System.out.println("[예외발생] 숫자가 아닙니다. 다시 입력~");
			}
		}
		
	}

	private void displayResult() {
		System.out.println("-----------------");
		System.out.println("> 입금액 : " + inMoney);
		System.out.println("> 판매액 : " + income);
		System.out.println("> 잔액 : " + change);
	}

	private void computeIncome() {
		//판매액계산 : 단가 * 주문수량
		switch (select) {
			case 1 : income = AMERICANO * count; break;
			case 2 : income = CAFE_LATTE * count; break;
			case 3 : income = CAFE_MOCA * count; break;
			case 4 : income = JUICE * count; break;
		}
		totalIncome += income; //총 매출액 구하기
	}

	private void displayMenu() {
		System.out.println("<메뉴>");
		System.out.println("1.아메리카노   2.카페라떼   3.카페모카   4.과일주스   0.종료");
		
	}
	
}
```
```java
public class CafeTest {

	public static void main(String[] args) {
		Cafe cafe = new Cafe();
		cafe.open();
	}
}

```
