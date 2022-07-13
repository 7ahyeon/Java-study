# StudentVO 사용 3명의 성적 처리 실습 해답
```java
public class StudentVO2 {
	//필드선언(변수선언: 클래스 전체영역에서 사용) -------
		//성명 - name : String
		//국어 - kor : int
		//영어 - eng : int
		//수학 - math : int
		//총점 - tot : int
		//평균 - avg : double
		private String name;
		private int kor;
		private int eng;
		private int math;
		private int tot;
		private double avg;

		//생성자 작성 ------------------
		//생성자 - 성명, 국어, 영어, 수학 점수를 입력받는 생성자
		//  총점, 평균 계산 처리 computeTotAvg() 사용
		public StudentVO2(String name, int kor, int eng, int math) {
			this.name = name;
			//this.kor = kor;
			//this.eng = eng;
			//this.math = math;
			setKor(kor);
			setEng(eng);
			setMath(math);
			
			computeTotAvg();
		}
		//메소드 작성 ------------------
		// setter, getter 작성
		// 국어, 영어, 수학 점수 변경시 총점, 평균 재계산 처리
		// 국어, 영어, 수학 점수는 0~100 까지 값만 입력처리
		public String getName() {
			return name;
		}

		public void setName(String name) {
			this.name = name;
		}

		public int getKor() {
			return kor;
		}

		public void setKor(int kor) {
			if (kor >= 0 && kor <= 100) {
				this.kor = kor;
				computeTotAvg();
			} else {
				System.out.println("[예외] 0~100 범위가 아님");
			}
		}

		public int getEng() {
			return eng;
		}

		public void setEng(int eng) {
			if (eng >= 0 && eng <= 100) {
				this.eng = eng;
				computeTotAvg();
			} else {
				System.out.println("[예외] 0~100 범위가 아님");
			}
		}

		public int getMath() {
			return math;
		}

		public void setMath(int math) {
			if (math >= 0 && math <= 100) {
				this.math = math;
				computeTotAvg();
			} else {
				System.out.println("[예외] 0~100 범위가 아님");
			}
		}

		public int getTot() {
			return tot;
		}

		public void setTot(int tot) {
			this.tot = tot;
		}

		public double getAvg() {
			return avg;
		}

		public void setAvg(double avg) {
			this.avg = avg;
		}
		
		public void computeTotAvg() {
			this.tot = kor + eng + math;
			this.avg = tot * 100 / 3 / 100.0;
		}
		
		@Override
		public String toString() {
			return "StudentVO [name=" + name + ", kor=" + kor + ", eng=" + eng + ", math=" + math + ", tot=" + tot
					+ ", avg=" + avg + "]";
		}
}
```
```java
public class StudentManager2 {
	static final String TITLE = "성명\t국어\t영어\t수학\t총점\t평균";
	static final String LINE = "============================================";

	public static void main(String[] args) {
		/* (실습) 3명의 성적처리(StudentVO 사용)
		"홍길동", 100, 90, 81
		"이순신", 95, 88, 92
		"김유신", 90, 87, 77
		==============================
		성명\t국어\t영어 수학 총점 평균
		------------------------------
		홍길동	100	90	81	271	90.33
		이순신	95	88	92	275	91.66
		김유신	90	87	77	254	84.66
		*/		
		StudentVO2 stu1 = new StudentVO2("홍길동", 100, 90, 81);
		StudentVO2 stu2 = new StudentVO2("이순신", 95, 88, 92);
		StudentVO2 stu3 = new StudentVO2("김유신", 90, 87, 77);
		//stu1.computeTotAvg();
		System.out.println(stu1);
		System.out.println(stu2);
		System.out.println(stu3);
		System.out.println("----------");
		//stu1.setKor(99);
		
		System.out.println(LINE);
		System.out.println(TITLE);
		System.out.println(LINE);
		
//		System.out.println(stu1.getName() + "\t" + stu1.getKor() + "\t" + stu1.getEng() + "\t" 
//				+ stu1.getMath() + "\t" + stu1.getTot() + "\t" + stu1.getAvg());
		printData(stu1);
		printData(stu2);
		printData(stu3);
		System.out.println("=====================");
		
		System.out.println("=== 배열에 담아서 사용 ======");
		StudentVO2[] students = new StudentVO2[3];
		students[0] = stu1;
		students[1] = stu2;
		students[2] = stu3;
		
		printData(students);
		System.out.println("---------");
		
		System.out.println(">>> 성명, 총점, 평균 값 출력");
		for (int i = 0; i < students.length; i++) {
			String name = students[i].getName();
			int tot = students[i].getTot();
			double avg = students[i].getAvg();
			System.out.println(name + ", " + tot + ", " + avg);
		}
		
		

	}
	
	static void printData(StudentVO2 vo) {
		System.out.println(vo.getName() + "\t"
				+ vo.getKor() + "\t"
				+ vo.getEng() + "\t"
				+ vo.getMath() + "\t"
				+ vo.getTot() + "\t"
				+ vo.getAvg() );
	}
	
	static void printData(StudentVO2[] students) {
		for (StudentVO2 student : students) {
			printData(student);
		}
	}

}
```
```java
StudentVO [name=홍길동, kor=100, eng=90, math=81, tot=271, avg=90.33]
StudentVO [name=이순신, kor=95, eng=88, math=92, tot=275, avg=91.66]
StudentVO [name=김유신, kor=90, eng=87, math=77, tot=254, avg=84.66]
----------
============================================
성명	국어	영어	수학	총점	평균
============================================
홍길동	100	90	81	271	90.33
이순신	95	88	92	275	91.66
김유신	90	87	77	254	84.66
=====================
=== 배열에 담아서 사용 ======
홍길동	100	90	81	271	90.33
이순신	95	88	92	275	91.66
김유신	90	87	77	254	84.66
---------
>>> 성명, 총점, 평균 값 출력
홍길동, 271, 90.33
이순신, 275, 91.66
김유신, 254, 84.66
```



















