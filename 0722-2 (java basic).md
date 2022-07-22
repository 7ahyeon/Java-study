# Stack

**Stack class**

 - 바닥이 막힌 박스 형태 (접근 통로가 하나)
 - 후입 선출 : LIFO (Last In First Out)
 - 주요 메서드 : push(), peek(), pop()

```java
Stack<String> stack = new Stack<String>();
System.out.println("stack.empty() : " + stack.empty());

System.out.println("---push() : 데이터 입력---");
stack.push("1. 첫번째"); // Stack method 
stack.push("2. 두번째");
stack.add("3. 세번째"); //Vector method (list)
stack.push("4. 네번째"); 

System.out.println("stack : " + stack);
System.out.println("stack.size() : " + stack.size());
System.out.println("stack.empty() : " + stack.empty());

System.out.println("---peek() : 데이터 확인---");

System.out.println("stack.peek() : " + stack.peek());
System.out.println("stack.peek() : " + stack.peek());
System.out.println("stack.peek() : " + stack.peek());

System.out.println("stack : " + stack);
System.out.println("stack.size() : " + stack.size());
System.out.println("stack.empty() : " + stack.empty());

System.out.println("---pop() : 데이터 꺼내기---");
// 단, 데이터가 없을시 EmptyStackException 발생
System.out.println("stack.pop() : " + stack.pop());
System.out.println("stack.pop() : " + stack.pop());
System.out.println("stack.pop() : " + stack.pop());
System.out.println("stack.pop() : " + stack.pop());
//		System.out.println("stack.pop() : " + stack.pop()); //EmptyStackException

System.out.println("stack : " + stack);
System.out.println("stack.size() : " + stack.size());
System.out.println("stack.empty() : " + stack.empty());
```







# Queue

**Queue interface**

 - 양쪽이 뚫린 파이프 형태 (접근 통로가 둘)
 - Queue interface 구현 -> LinkedList class
 - 선입 선출 : FIFO (First In First Out)
 - 주요 메서드 : offer(), poll(), peek()
