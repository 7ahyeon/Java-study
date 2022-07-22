# Scanner 사용 성적 처리 2

```java
public class ScannerSungjuk {
private Scanner scan = new Scanner(System.in);
private String name;
private int kor;
private int eng;
private int math;
private int tot;
private double avg;

public void start() {
	while (true) {			
		// 입력---
		input(); 

		// 처리---
		process();

		// 출력---
		output();
		
		System.out.println("------");
			System.out.print(">> 종료하려면 0을 입력해주십시오 : ");
			String answer = scan.nextLine();
			if (answer.equals("0")) {
				System.out.println("---성적 처리 종료---");
				break;
			}
	}
}

void input() {
  System.out.println("----------");
  System.out.print("성명 : ");
  name = scan.next();

  System.out.print("국어 : ");
  kor = scan.nextInt();

  System.out.print("영어 : ");
  eng = scan.nextInt();
  scan.nextLine(); // 줄바꿈 문자까지의 값 읽어서 없애기
  // 주의 : next(), nextXxx()등의 뒤에 nextLine()사용시 발생오류 해결용

  System.out.print("수학 : ");
  math = Integer.parseInt(scan.nextLine());

  System.out.println("----------");
}

void process() {
  tot = kor + eng + math;
  avg = tot * 100 / 3 / 100.0;
}

void output() {
  System.out.println("성명 : " + name);
  System.out.println("국어 : " + kor);
  System.out.println("영어 : " + eng);
  System.out.println("수학 : " + math);
  System.out.println("----------");
  System.out.println("평균 : " + tot);
  System.out.println("총점 : " + avg);
  System.out.println("----------");
}
}

```
```java
public class ScannerSungjukMain {

	public static void main(String[] args) {
		System.out.println("---main() 시작---");
//		ScannerSungjuk sungjuk = new ScannerSungjuk();
//		sungjuk.start();
		
		new ScannerSungjuk().start();
		System.out.println("---main() 종료---");	
	}
}
```


















