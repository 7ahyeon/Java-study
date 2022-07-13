# 2차원 배열을 사용한 성적 처리 실습 해답

**static final String 변수명 = "";**
- 클래스와 메인 사이 위치

```java
static final String TITLE = "국어\t영어\t수학\t총점\t평균";
	static final String LINE = "-------------------------------------";

	public static void main(String[] args) {
		int[][] sungjuk = { {100, 90, 80},
							{100, 90, 81}, 
							{100, 90, 80}};
		
		System.out.println(Arrays.toString(sungjuk));
		int kor = 0;
		int eng = 0;
		int math = 0;
		int tot = 0;
		double avg = 0;

		dispTitle();
		for (int i = 0; i < sungjuk.length; i++) {
			kor = sungjuk[i][0];
			eng = sungjuk[i][1];
			math = sungjuk[i][2];
			tot = kor + eng + math;
			avg = tot * 100 / 3 / 100.0; 
			
			System.out.println(kor + "\t" + eng+ "\t" + math + "\t" + tot + "\t" + avg);
		}
		
		
	} //main

	static void dispTitle() {
		System.out.println(LINE);
		System.out.println(TITLE);
		System.out.println(LINE);
	}
```







