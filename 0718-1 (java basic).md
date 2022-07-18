
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
# method overloading vs overriding

**메서드 오버로딩 method overloading**
- 중복 선언 / 동일 기능
- 다른 메서드 동일 메서드명 사용 가능
- 1개 클래스 내에서 적용 (상속 X)
- printBoolean(boolean), printInt(int), ... , printObject(object) : print()
- 

**메서드 오버라이딩 method overrriding**
- 서로 다른 기능
- 상속 관계 메서드 재정의
- 상위 클래스 toString : 주소값 출력 -> 하위 클래스 toString : 객체 속성값 출력










