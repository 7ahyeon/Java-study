# Map을 사용한 성적 처리 실습

```java
StudentVO stu1 = new StudentVO("홍길동", 100, 90, 81);
StudentVO stu2 = new StudentVO("이순신", 95, 88, 92);
StudentVO stu3 = new StudentVO("김유신", 90, 87, 77);

HashMap<String, StudentVO> map = new HashMap<>();
map.put("홍길동", stu1);
map.put("이순신", stu2);
map.put("김유신", stu3);

System.out.println("성명\t국어\t영어\t수학\t총점\t평균");

Set<String> KeySet = map.keySet();

for (String key : KeySet) {
  printData(map.get(key));
}


System.out.println("---전체 데이터 출력---");

for (String key : KeySet) {
  if (map.get(key).getName().equals("김유신")) {
    map.get(key).setKor(95);
  }
  printData(map.get(key));
}

System.out.println("---김유신 데이터 출력---");

for (String key : KeySet) {
  if (map.get(key).getName().equals("김유신")) {
    printData(map.get(key));
  }
}

//전체 데이터 출력 메서드
System.out.println("---전체 데이터 출력 메서드---");
printData(map, KeySet);

}
static void printData(StudentVO vo) { //list에 담아두고 기능은 StudentVO를 이용
System.out.println(vo.getName() + "\t" + 
           vo.getKor() + "\t" + 
           vo.getEng() + "\t" + 
           vo.getMath() + "\t" + 
           vo.getTot() + "\t" + 
           vo.getAvg());	
}

static void printData(HashMap<String, StudentVO> map, Set<String> KeySet) {
for (String key : KeySet) {
  printData(map.get(key));
}
}
```







