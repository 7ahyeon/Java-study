# 숫자 추측 게임 실습

- 컴퓨터가 1~100 사이의 숫자를 정하면 사람이 맞추는 게임
- 선택 기회 5회

- Math.random() : 0 <= random값 < 1 범위의 실수값 
- 컴숫자 : 70 인 경우 
- 사람이 선택한 숫자(80)가 크면 : 작다는 메시지 출력
- 사람이 선택한 숫자(50)가 작으면 : 크다는 메시지 출력
- 5번 이내에 맞추면 : 성공!!! n번 만에 맞췄습니다.(화면출력)
- 5번을 넘기면 : 실패~~ 내가 생각한 숫자는 70입니다.(화면출력)

- 다시 도전하시겠습니까?(y,n) 

```java
public class GuessNumberGame {
	
	private int num;
	private int guessNum;
	private int chance = 0;
	
	private Scanner scan;
	
	
	public GuessNumberGame() {
		scan = new Scanner(System.in);
	}

	public GuessNumberGame(Scanner scan) {
		this.scan = scan;
	}

	public void start() {
		while (true) {
			if (! game()) {
				System.out.println("[실패] 맞출 숫자는 " + num + "이었습니다.");
			}
		}
	}
	
	public boolean game() {
		boolean isGamePlay = true;
		
		num = (int)(Math.random() * 99 + 1);
		showDisp();
		
		while (true) {
			
			int guessNum = selectPerson();
			checkNumber(num, guessNum);
			if (num == guessNum) {
				System.out.println("[성공] " + chance + "번 만에 맞췄습니다." );
			}
		if (chance == 5) {
			return false;
		}
		}
	}
	
	private void checkNumber(int num, int guessNum) {
		if (num < guessNum) {
			System.out.println(guessNum + "보다 작습니다.");
		} else if (num > guessNum) {
			System.out.println(guessNum + "보다 큽니다.");			
		} 
		chance++;
	}
	
	
	private int selectPerson() {
		System.out.println("어떤 숫자라고 생각하십니까? : ");
		int guessNum = 1; 
		while (true) {
			try {
				guessNum = Integer.parseInt(scan.nextLine());
				if (guessNum >= 1 && guessNum <= 100) {
					break;
				} else {
					System.out.println("1~100사이의 숫자가 아닙니다.");
				}
				break;				
			} catch (Exception e) {
				System.out.println("[오류] 숫자가 아닙니다.");
			}
		}
		return guessNum;
	}
	private void showDisp() {
		System.out.println("<숫자 추측 게임>");
		System.out.println("1~100사이의 숫자를 맞춰보세요.");
		System.out.println("기회는 5번입니다.");
	}
	
}

```
