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



