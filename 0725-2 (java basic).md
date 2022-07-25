# Scanner를 이용한 가위바위보 게임 실습 해답

```java
public class ScissorsGame {
	private static final String SCISSORS = "가위";
	private static final String ROCK = "바위";
	private static final String PAPER = "보";
	private static final String WIN_PERSON = "당신이 이겼습니다";
	private static final String WIN_COMPUTER = "사람패/컴퓨터승";
	private static final String DRAW = "무승부";

	public void start() {
		Scanner scan = new Scanner(System.in);
		System.out.println("<가위, 바위, 보 게임>");
		
		while (true) {
			//1. 컴퓨터가 선택
			int comSelect = (int) (Math.random() * 3 + 1);
			//comSelect = 1;
			//System.out.println("comSelect : " + comSelect);
			
			//2. 메뉴 표시
			System.out.println("가위, 바위, 보 중에 하나를 선택하시오~");
			System.out.println("1.가위   2.바위    3.보   0.종료");
			
			//3. 사람이 선택
			System.out.print(">> 당신의 선택은(1~3)? ");
			int select = scan.nextInt();
			//System.out.println("select : " + select);
			if (select == 0) {
				break;
			}
			
			//3-2. 선택숫자 ---> 문자열(가위, 바위, 보)
			String strComputer = "컴퓨터선택값";
			if (comSelect == 1) {
				strComputer = SCISSORS;
			} else if (comSelect == 2) {
				strComputer = ROCK;
			} else if (comSelect == 3) {
				strComputer = PAPER;
			}
			
			String strPerson = "사람선택값";
			switch (select) {
				case 1 : strPerson = SCISSORS; break;
				case 2 : strPerson = ROCK; break;
				case 3 : strPerson = PAPER; break;
			}
			//System.out.println("컴퓨터 : " + strComputer + ", 사람: " + strPerson);
			
			//4. 결과 판정
			//com 1, person: 1
			String result = "판정안됨";
			if (strComputer.equals(strPerson)) {
				result = DRAW;
			}
			if (strComputer.equals(SCISSORS)) {
				if (strPerson.equals(ROCK)) {
					//System.out.println("사람승/컴퓨터패");
					result = WIN_PERSON;
				}
				if (strPerson.equals(PAPER)) {
					//System.out.println("사람패/컴퓨터승");
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
			
			//5. 결과 출력
			System.out.println(">>판정결과 : " + result + ", 컴퓨터 : " + strComputer);
			System.out.println("---------------------");
			System.out.println();
		
		}
		
		System.out.println(":::: 게임을 종료했습니다~~");
		
	}

}

```
```java
public static void main(String[] args) {
  ScissorsGame2 game = new ScissorsGame2();
  game.start();

}
```
```java
<가위, 바위, 보 게임>
가위, 바위, 보 중에 하나를 선택하시오~
1.가위   2.바위    3.보   0.종료
>> 당신의 선택은(1~3)? 1
>>판정결과 : 무승부, 컴퓨터 : 가위
---------------------

```
