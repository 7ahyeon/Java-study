# StudentVO 사용 3명의 성적 처리

**VO (Value Object)**
- 자바 빈(JavaBean) 형태의 클래스 작성 
- 데이터(값)을 저장하기 위한 클래스(객체)
- 명명 : Student, StudentVo, StudentVO

```java
public class StudentVO {

	//field 선언 ---
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
		
	//생성자 작성 ---
	//생성자 - 성명, 국어, 영어, 수학 점수를 입력 받는 생성자
	// 총점, 평균 계산 처리 computeToAvg() 사용


	public StudentVO(String name, int kor, int eng, int math) {
		super();
		this.name = name;
		this.kor = kor;
		this.eng = eng;
		this.math = math;
		computeTotAvg();
	}
		
	//method 작성 ---
	//setter, getter 작성
	//국어, 영어, 수학 점수 변경시 총점, 평균 재계산 처리
	//국어, 영어, 수학 점수는 0-100까지의 값만 입력 처리
		
	public void setName(String name) {
		this.name = name;
	}

	public String getName() {
		return name;
	}
		
	public void setKor(int kor) {
		if (kor >= 0 && kor <= 100) {
			this.kor = kor;
			computeTotAvg();
		} else {
			System.out.println("[오류] 1-100의 범위를 벗어났습니다.");
		}
	}
		
	public int getKor() {
		return kor;
	}
		
	public void setEng(int eng) {
		if (eng >= 0 && eng <= 100) {
			this.eng = eng;
			computeTotAvg();
		} else {
			System.out.println("[오류] 1-100의 범위를 벗어났습니다.");
		}
	}
		
	public int getEng() {
		return eng;
	}
	public void setMath(int math) {
		if (math >= 0 && math <= 100) {
			this.math = math;
			computeTotAvg();
		} else {
			System.out.println("[오류] 1-100의 범위를 벗어났습니다.");
		}
	}
		
	public int getMath() {
		return math;
	}

	public void setTot(int tot) {
		this.tot = tot;
	}
		
	public int getTot() {
		return tot;
	}

	public void setAvg(double avg) {
		this.avg = avg;
	}

	public double getAvg() {
		return avg;
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
```
```java
static final String TITLE = "성명\t국어\t영어\t수학\t총점\t평균";
static final String LINE = "----------------------------------------------";

	
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
		
	StudentVO stu1 = new StudentVO("자바1", 100, 90, 81);
	StudentVO stu2 = new StudentVO("자바2", 95, 88, 92);
	StudentVO stu3 = new StudentVO("자바3", 90, 87, 77);
		
	System.out.println(LINE);
	System.out.println(TITLE);
	System.out.println(LINE);
	TOTAL(stu1, stu2, stu3);
		
	stu1.setKor(70);
	stu2.setKor(50);
	stu3.setKor(70);
	
	System.out.println(LINE);
	System.out.println(TITLE);
	System.out.println(LINE);
	TOTAL(stu1, stu2, stu3);

}

static void TOTAL(StudentVO a, StudentVO b, StudentVO c) {
	System.out.println(a.getName() + "\t" + a.getKor() + "\t" + a.getEng() + "\t" + a.getMath() + "\t" + a.getTot() + "\t" + a.getAvg());
	System.out.println(b.getName() + "\t" + b.getKor() + "\t" + b.getEng() + "\t" + b.getMath() + "\t" + b.getTot() + "\t" + b.getAvg());
	System.out.println(c.getName() + "\t" + c.getKor() + "\t" + c.getEng() + "\t" + c.getMath() + "\t" + c.getTot() + "\t" + c.getAvg());
		
}
```















