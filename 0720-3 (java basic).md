# List를 사용한 성적 처리 실습

- 사용클래스명 : StudentVO, StudentListManager - main() 메소드
1. 3명의 학생데이터(성명,국어,영어,수학)를 StudentVO 클래스를 이용해서 만들고
- "홍길동", 100, 90, 81
- "이순신", 95, 88, 92
- "김유신", 90, 87, 77
2. ArrayList 타입의 변수(list)에 저장하고
3. list에 있는 데이터를 사용해서 전체 데이터 화면출력
- 성명    국어   영어  수학    총점     평균
- 홍길동   100  90  81  270  90.33
4. 김유신 국어 점수를 95 점으로 수정 후 김유신 데이터만 출력

```java
public class StudentVO {

	private String name;
	private int kor;
	private int eng;
	private int math;
	private int tot;
	private double avg;
	
	public void StudentVO() {
	}

	public StudentVO(String name, int kor, int eng, int math) {
		super();
		this.name = name;
		this.kor = kor;
		this.eng = eng;
		this.math = math;
		computeTotAvg();
	}

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
			System.out.println("[오류] 1-100의 범위를 벗어났습니다");
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
			System.out.println("[오류] 1-100의 범위를 벗어났습니다");
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
			System.out.println("[오류] 1-100의 범위를 벗어났습니다");
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
		tot = kor + eng + math;
		avg = tot * 100 / 3 / 100.0;
	}
	
}
```
```java
public class StudentListManager {

public static void main(String[] args) {
	StudentVO stu1 = new StudentVO("홍길동", 100, 90, 81);
	StudentVO stu2 = new StudentVO("이순신", 95, 88, 92);
	StudentVO stu3 = new StudentVO("김유신", 90, 87, 77);

	ArrayList<StudentVO> list = new ArrayList<>();
	list.add(stu1);
	list.add(stu2);
	list.add(stu3);

	System.out.println("성명\t국어\t영어\t수학\t총점\t평균");
	printData(stu1);
	printData(stu2);
	printData(stu3);

	System.out.println("---김유신 국어 점수 95---");
	list.get(2).setKor(95);
	printData(stu3);

}

static void printData(StudentVO vo) {
	System.out.println(vo.getName() + "\t" + 
			  vo.getKor() + "\t" + 
			   vo.getEng() + "\t" + 
			  vo.getMath() + "\t" + 
			   vo.getTot() + "\t" + 
			   vo.getAvg());	
	}	
}
```
