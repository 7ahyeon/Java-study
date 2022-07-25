# 숫자 추측 게임 실습 해답

```java
public class GuessNumberGame {
	private int comNo; // 컴퓨터가 생각한 숫자
	private int meNo; // 내가 정한 숫자
	private int tryCnt; //시도한 횟수
	private int min = 1; //선택 최저값
	private int max = 100; //선택 최고값
	private Scanner scan = new Scanner(System.in);

	public void startGame() {
		System.out.println(":::: 게임을 시작합니다");
		while (true) {
			playGame();
			if (! tryAgain()) {
				break;
			}
		}
		System.out.println(":::: 게임이 종료되었습니다");
	}

	private boolean tryAgain() {
		boolean result = true;
		//게임을 더 할건지 여부 체크
		System.out.println("컴) 다시 도전하시겠습니까(y/n)?" );
		String tryYesNo = scan.nextLine();
		if ("n".equalsIgnoreCase(tryYesNo)) {
			result = false;
		}
		return result;
	}

	private void playGame() {
		//1. 컴퓨터가 1~100까지 숫자 중 하나를 선택
		comNo = (int) (Math.random() * 100 + 1);
		System.out.println("컴) 1~100까지 숫자 중 하나를 생각했습니다. "
				+ "맞춰보세요~~");
		//System.out.println("> 컴퓨터가 생각한 숫자 : " + comNo);
		
		tryCnt = 0;
		min = 1; //선택 최저값
		max = 100; //선택 최고값
		while (tryCnt < 5) {
			tryCnt++;
			//2. 사람이 숫자 선택
			meNo = selectNumber();
			//System.out.println("> 사람 선택 숫자 : " + meNo);
			if (meNo < min || meNo > max) {
				System.out.println("컴) 범위 확인하고 다시 선택하세요~~");
				tryCnt--;
				continue;
			}
			
			//3. 사람선택 숫자와 컴퓨터 숫자 비교 판정
			if (comNo == meNo) {
				System.out.println("컴) 성공!!! 맞췄습니다. "
						+ "내가 생각한 숫자는 " + comNo + "입니다");
				break;
			}
			if (comNo > meNo) {
				System.out.println("컴) " + meNo + " 보다 큽니다");
				min = meNo + 1;
			}
			if (comNo < meNo) {
				System.out.println("컴) " + meNo + " 보다 작습니다");
				max = meNo - 1;
			}
			
			// 5번시도하고 여기까지 왔으면 실패
			if (tryCnt == 5) {
				System.out.println("컴) 실패!!!! "
						+ "내가 생각한 숫자는 " + comNo + "입니다");
			}
		}
		System.out.println("::: 게임이 끝났습니다");
		System.out.println("---------------------\n");
		
	}

	private int selectNumber() {
		int number = -1;
		while (true) {
			try {
				System.out.print(tryCnt + "번째> 숫자를 선택 (" + min + "~" + max + ") : ");
				number = Integer.parseInt(scan.nextLine());
				break;
			} catch (Exception e) {
				System.out.println("[주의] 숫자값을 입력하세요.");
			}
		}
			
		return number;
	}
	
}

```
```java

```

