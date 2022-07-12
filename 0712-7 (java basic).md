# 2차원 배열을 사용한 성적 처리 실습
1. 국어, 영어, 수학 점수 3개를 저장한 2차원 배열(sungjuk) 생성
2. 3명 성적을 입력하고 개인별 총점과 평균을 계산하여 화면에 데이터 출력
- 국어  영어  수학  총점  평균
- 100  90  80  270 90.0
- 100  90  81  271 90.33
- 100  90  80  270 90.0

```java
	int[] kor = {100, 100, 100};
	int[] eng = {90, 90, 90};
	int[] math = {80, 81, 80};
	int[][] sungjuk = {kor, eng, math};
	
	int[] sum = new int[3];
	double[] avg = new double[3];
	for (int i = 0; i < sungjuk.length; i++) {
		for (int k = 0; k < sungjuk[i].length; k++) {
			sum[i] += sungjuk[k][i];
			avg[i] = sum[i] * 100 / sungjuk.length / 100.0;
		}
		System.out.println("개인별 총점 : " + sum[i]); 
		System.out.println("평균 : " + avg[i]); 
	}
```
