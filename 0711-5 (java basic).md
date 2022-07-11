- System.out.print("\t"); 옆으로 한 칸
- System.out.print("\n"); 줄바꿈

# StringBuffer Class

**StringBuffer**
- 참조형 데이터는 객체 생성 타입(new)으로 사용 가능
```java
StringBuffer sb = new StringBuffer();
StringBuffer sb1 = "Hello" // 사용 불가능 (Type mismatch)
```
```java
System.out.println("sb.length() : " + sb.length()); // 데이터 크기 기본 0
System.out.println("sb.capacity() : " + sb.capacity()); // 저장  기본 16
```
```java
StringBuffer sb = new StringBuffer("Hello Java!");
		
System.out.println("sb.length() : " + sb.length()); // 데이터 크기 : 11
System.out.println("sb.capacity() : " + sb.capacity()); // 기본 + 데이터 크기 = 27
```

1. **문자열 데이터 추가 (append)**
- 문자열.append("추가 문자") : length 영향O / capacity 영향X 
- 문자열.append("추가").append("문자") : chainning 가능

```java
sb.append(" 반갑습니다");
		
System.out.println(sb); //Hello Java! 반갑습니다
System.out.println("sb.length() : " + sb.length()); //11+6 = 17
System.out.println("sb.capacity() : " + sb.capacity()); // 27
```

2. **문자열 뒤집기 (reverse)**
- 문자열.reverse()
```java
sb.reverse();
System.out.println("sb.reverse() 실행 후 : " + sb); //다니습갑반 !avaJ olleH
System.out.println(sb.reverse()); //Hello Java! 반갑습니다
```

3. **문자열 데이터 삭제 (delete)**
- 문자열.delete() : length 영향O / capacity 영향X 
```java
System.out.println("sb.delete(0, 6) : " + sb.delete(0, 6)); //Java! 반갑습니다
System.out.println("sb : " + sb); //Java! 반갑습니다
System.out.println("sb.length() : " + sb.length()); //11
System.out.println("sb.capacity() : " + sb.capacity()); //27
```

4. **문자열 데이터 삽입 (insert)**
- 문자열.insert() : length 영향O / capacity 영향X 
```java
System.out.println("sb.insert(0, \"Hello \") : " + sb.insert(0, "Hello ")); //Hello Java! 반갑습니다
System.out.println("sb : " + sb); //Hello Java! 반갑습니다
System.out.println("sb.length() : " + sb.length()); //11+6 = 17
System.out.println("sb.capacity() : " + sb.capacity()); //27
		
5. **문자열 데이터 변경 (replace)**
- 문자열.reverse() : length 영향O / capacity 영향X
```java
System.out.println("sb.replace(0, 5, \"Hi\") : " + sb.replace(0, 5, "Hi")); //Hi Java! 반갑습니다
System.out.println("sb : " + sb); //Hi Java! 반갑습니다
System.out.println("sb.length() : " + sb.length()); // 17-5+2 = 14
System.out.println("sb.capacity() : " + sb.capacity()); //27
```

6. **문자열 사이즈 변경 (trimToSize)
- 문자열.trimToSize() : capacity = length (저장 용량을 현재 문자열 길이로 변경)
```java
sb.trimToSize();

System.out.println("sb : " + sb); //Hi Java! 반갑습니다
System.out.println("sb.length() : " + sb.length()); // 14
System.out.println("sb.capacity() : " + sb.capacity()); // 14

System.out.println(">>>append() 실행 후");
sb.append(" 자바 공부중~"); //8
System.out.println("sb : " + sb); //Hi Java! 반갑습니다 자바 공부중~
System.out.println("sb.length() : " + sb.length()); //22
System.out.println("sb.capacity() : " + sb.capacity());  //30 (14+8+(8) : 문자열 + 8)
		
```

7. **문자열 길이 조절 (setLength)**
- 문자열.setLength(n) : n번째 제외 삭제 :  length 영향O / capacity 영향X 
```java
sb2 : 안녕하세요반갑습니다!
sb2.length() : 11
sb2.capacity() : 11

sb2.setLength(6); //데이터 크기 설정(작게 설정하면 delete 효과)
System.out.println("sb2 : " + sb2); // 안녕하세요반
System.out.println("sb2.length() : " + sb2.length()); // 6
System.out.println("sb2.capacity() : " + sb2.capacity()); //11 
```


  



