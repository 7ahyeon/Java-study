# Scanner를 이용한 가위바위보 게임 실습 해답 정리

```java
public class ScissorsGame3 {
	private static final String SCISSORS = "가위";
	private static final String ROCK = "바위";
	private static final String PAPER = "보";
	private static final String WIN_PERSON = "당신이 이겼습니다";
	private static final String WIN_COMPUTER = "사람패/컴퓨터승";
	private static final String DRAW = "무승부";

	private Scanner scan;
	
	
	public ScissorsGame3() {
		scan = new Scanner(System.in);
	}

	public ScissorsGame3(Scanner scan) {
		this.scan = scan;
	}

	public void start() {
		while (true) {
			if (!isGamePlay()) {
				System.out.println(">> 게임을 중단합니다.");
				break;
			}
		}
	
	}
	private boolean isGamePlay() {
		boolean isContinueGame = true;
		
		//1. 컴퓨터 선택
		int comSelect = selectComputer();
		
		//2. 메뉴출력
		showMenu();
		
		//3. 사람선택
		int select = selectPerson();
		if (select == 0) {
			return false;
		}
		
		//3-2. 선택 숫자 -> 문자열 (가위바위보)
		String strComputer = changeNumberToString(comSelect);
		String strPerson = changeNumberToString(select);
		
		//4. 결과 판정 
		String result = checkWinner(strComputer, strPerson);
		
		//5. 판정 결과 출력
		System.out.println(">>판정 결과 : " + result + ", 컴퓨터 : " + strComputer);
		System.out.println("---------------------\n");
		
		return isContinueGame;
		
	}

	private String checkWinner(String strComputer, String strPerson) {
		String result = "판정안됨";
		if (strComputer.equals(strPerson)) {
			result = DRAW;
		}
		if (strComputer.equals(SCISSORS)) {
			if (strPerson.equals(ROCK)) {
				result = WIN_PERSON;
			}
			if (strPerson.equals(PAPER)) {
				result = WIN_COMPUTER;
			}
		}
		if (strComputer.equals(ROCK)) { //바위
			if (strPerson.equals(SCISSORS)) {
				result = WIN_COMPUTER;
			} 
			if (strPerson.equals(PAPER)) {
				result = WIN_PERSON;
			}
		}
		if (strComputer.equals(PAPER)) { //보
			if (strPerson.equals(SCISSORS)) {
				result = WIN_PERSON;
			} 
			if (strPerson.equals(ROCK)) {
				result = WIN_COMPUTER;
			}
		}
		return result;
	}

	private String changeNumberToString(int select) {
		String result = "변환 안 됨";
		switch (select) {
			case 1 : result = SCISSORS; break;
			case 2 : result = ROCK; break;
			case 3 : result = PAPER; break;
	}
		return result;
	}

	private int selectPerson() {
		int select = -1;
		while (true) {
			try {
				System.out.print(">> 당신의 선택은(1~3)? ");
				select = Integer.parseInt(scan.nextLine());
				if (select >= 0 && select <= 3) {
					break;
				} else {
					System.out.println("1~3범위의 숫자를 선택하세요.");
				}
				break;
			} catch(Exception e) {
				System.out.println("[오류] 숫자를 입력하세요.");
			}			
		}
		return select;
	}

	private void showMenu() {
		System.out.println("가위, 바위, 보 중에 하나를 선택하시오~");
		System.out.println("1.가위   2.바위    3.보   0.종료");
	}

	private int selectComputer() {
		return (int) (Math.random() * 3 + 1);
	}

}
```
