# Java-study

**DTO (Data Transfer Object)**
- 데이터(값)을 저장하고 전송하기 위한 클래스(객체)
- 명명 : Student, StudentDTO, StudentDto

# 숫자 3개 중 가장 큰 수 구하기 최대값 찾기 실습
```java
int max = Integer.MIN_VALUE;

int[] num = {30, 60, 20};
for (int i = 0; i < num.length; i++){
  if (num[i] > max) {
    max = num[i];
    }
}
System.out.println(">> 가장 큰 수 : " + max);			
```

# 숫자 5개 중 가장 큰 수 구하기 최대값 찾기 실습

```java
int[] num2 = {30, 60, 20, 15, 70};
for (int i = 0; i < num2.length; i++){
  if (num2[i] > max) {
    max = num2[i];
  }
}
System.out.println(">> 가장 큰 수 : " + max);			
```
	



