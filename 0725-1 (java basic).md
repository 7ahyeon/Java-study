# Scanner를 이용한 가위바위보 게임 실습

- 컴퓨터와 함께하는 가위바위보 게임
0. 컴퓨터가 가위(1),바위(2),보(3) 선택(Math.random())
1. 1.가위, 2.바위, 3.보   0.종료   선택 메뉴 출력 
2. 선택값 입력
3. 결과 비교 후 승자, 패자 결정
4. (반복) 게임 반복 진행 : 0 선택시 종료 처리

```java
public class ScissorsGame {
	private	Scanner scan = new Scanner(System.in);
	private	int comSelect;
	private	int select;
	
	/* Scanner를 이용한 가위, 바위 , 보 게임 *******
	컴퓨터와 함께하는 가위,바위,보 게임
		0. 컴퓨터가 가위(1),바위(2),보(3) 선택(Math.random())
		1. 1.가위, 2.바위, 3.보   0.종료   선택 메뉴 출력 
		2. 선택값 입력
		3. 결과 비교 후 승자, 패자 결정
		(반복) 게임 반복 진행 - 0 선택시 종료 처리
	=============================== */

	public ScissorsGame() {
		scan = new Scanner(System.in);
	}	
	public ScissorsGame(Scanner scan) {
		this.scan = scan;
	}	

	public void game() {
		while (true) {
			start();
			if (select == 0) {
				System.out.println("게임을 종료합니다.");
				break;
			}
			disp();
		}
	}
	
	private void start() {
		while (true) {
			try {
				comSelect = (int)(Math.random()*3+1);
				
				System.out.println("< 가위바위보 게임 >");
				System.out.println("가위바위보 중에 하나를 선택하시오.");
				System.out.println("1.가위 2.바위 3.보 0.종료");
				System.out.println(">> 당신의 선택은 ? ");
				select = Integer.parseInt(scan.nextLine());
				if (select < 0 || select > 3) {
					System.out.println("0~3 범위의 숫자를 선택하세요.");
					continue;
					}
				break;
			} catch (Exception e) {
					System.out.println("[예외 발생] 숫자가 아닙니다.");
			}
		}
	}
	
	private void disp() {
		switch (comSelect) {
		case 1 : if (select == 2) {
					one(); vic();
				} else if (select ==1 ) {
					one(); tie();
				} else {
					one(); lose();
				} break;
		case 2 : if (select == 3) {
					two(); vic();
				} else if (select ==2 ) {
					two(); tie();
				} else {
					two(); lose();
				} break;
		case 3 : if (select == 1) {
					three(); vic();
				} else if (select ==3 ) {
					three(); tie();
				} else {
					three(); lose();
				} break;
		}
	}
	
	static void one() {
		System.out.print("컴퓨터가 가위를 내서");
	}
	static void two() {
		System.out.print("컴퓨터가 바위를 내서");
	}
	static void three() {
		System.out.print("컴퓨터가 보자기를 내서");
	}
	static void vic() {
		System.out.println(" 승리하셨습니다.");
	}
	static void tie() {
		System.out.println(" 무승부입니다.");
	}
	static void lose() {
		System.out.println(" 패배하셨습니다.");
	}
	
}
```
```java
public static void main(String[] args) {
		ScissorsGame g1 = new ScissorsGame();
		g1.game();
	}
```
```java
< 가위바위보 게임 >
가위바위보 중에 하나를 선택하시오.
1.가위 2.바위 3.보 0.종료
>> 당신의 선택은 ? 
1
컴퓨터가 가위를 내서 무승부입니다.
```

























