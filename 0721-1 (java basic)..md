#  Set 이용 로또 만들기 실습

1. 1~45 랜덤숫자 6개를 Set에 저장
2. 로또번호 6개를 추첨해서 Set 에 저장하고 화면 출력
- Math.random() : 0.0 ~ 0.999999.. 실수형 데이터 생성(0 <= ran < 1)
- Math.random() 사용 : (int)(Math.random() * 45 + 1)
3. 출력은 작은 숫자부터 큰 숫자 형태로
- 예) 금주의 로또번호 : 5, 8, 10, 25, 33, 41 

```java
Set<Integer> lottoSet = new HashSet<>();

while (lottoSet.size() < 6) { //중복값 저장 안되므로 사이즈로 판단
  lottoSet.add((int)(Math.random() * 45 + 1));
}

ArrayList<Integer> lottoList = new ArrayList<>(lottoSet);
Collections.sort(lottoList); // Set 사용 X List 사용 O
System.out.println("금주의 로또 번호 : " + lottoList);
```

**TreeSet**

```java
// TreeSet : 데이터를 정렬해서 저장 
TreeSet<Integer> lottoSet = new TreeSet<>();

while (lottoSet.size() < 6) { //생성은 무작위
  lottoSet.add((int)(Math.random() * 45 + 1));
}
System.out.println("로또 번호 : " + lottoSet);
```
# Set을 사용한 성적 처리 실습

```java
  StudentVO stu1 = new StudentVO("홍길동", 100, 90, 81);
  StudentVO stu2 = new StudentVO("이순신", 95, 88, 92);
  StudentVO stu3 = new StudentVO("김유신", 90, 87, 77);

  HashSet<StudentVO> set = new HashSet<>();
  set.add(stu1);
  set.add(stu2);
  set.add(stu3);

  System.out.println("---개선된 for문---");
  title();
  for (StudentVO vo : set) {
    printData(vo);
  }
  System.out.println("---Iterator 사용---");

  Iterator<StudentVO> ite = set.iterator();
  while (ite.hasNext()) {
    printData(ite.next());
  }

  System.out.println("---김유신 국어 점수 변경 처리---");
  for (StudentVO vo : set) {
    if (vo.getName().equals("김유신")) {
      vo.setKor(95);
      break;
    }
  }
  System.out.println(">> 변경 후 전체 데이터 확인");
  printData(set);

  System.out.println("---김유신 학생 정보만 출력---");
  for (StudentVO vo : set) {
    if (vo.getName().equals("김유신")) {
      printData(vo);				
    }
  }

	}
	static void title() {
		System.out.println("성명\t국어\t영어\t수학\t총점\t평균");
	}

	static void printData(StudentVO vo) { 
		System.out.println(vo.getName() + "\t" + 
						   vo.getKor() + "\t" + 
						   vo.getEng() + "\t" + 
						   vo.getMath() + "\t" + 
						   vo.getTot() + "\t" + 
						   vo.getAvg());	
	}	
	
	static void printData(HashSet<StudentVO> set) {
		for (StudentVO vo : set) {
			printData(vo);
		}
	}

}

```









