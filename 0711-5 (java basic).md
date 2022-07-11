- System.out.print("\t"); 옆으로 한 칸
- System.out.print("\n"); 줄바꿈

# StringBuffer Class

**StringBuffer**
- 참조형 데이터는 객체 생성 타입(new)으로 사용 가능
```java
StringBuffer sb = new StringBuffer();

System.out.println("sb.length() : " + sb.length()); // 데이터 크기 기본 0
System.out.println("sb.capacity() : " + sb.capacity()); // 저장 공간 기본 16
```
- StringBuffer sb1 = "Hello" : 사용 불가능 (Type mismatch)
- 

