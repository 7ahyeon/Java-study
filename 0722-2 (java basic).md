# Stack

**Stack class**

 - 바닥이 막힌 박스 형태 (접근 통로가 하나)
 - 후입 선출 : LIFO (Last In First Out)
 - 주요 메서드 : push(), peek(), pop() (add() 사용 가능)

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

System.out.println("stack.peek() : " + stack.peek()); // 후입 선출 : 마지막 데이터부터 확인
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
//System.out.println("stack.pop() : " + stack.pop()); //EmptyStackException

System.out.println("stack : " + stack);
System.out.println("stack.size() : " + stack.size());
System.out.println("stack.empty() : " + stack.empty());
```
```java
stack.empty() : true
---push() : 데이터 입력---
stack : [1. 첫번째, 2. 두번째, 3. 세번째, 4. 네번째]
stack.size() : 4
stack.empty() : false
---peek() : 데이터 확인---
stack.peek() : 4. 네번째 
stack.peek() : 4. 네번째
stack.peek() : 4. 네번째
stack : [1. 첫번째, 2. 두번째, 3. 세번째, 4. 네번째]
stack.size() : 4
stack.empty() : false
---pop() : 데이터 꺼내기---
stack.pop() : 4. 네번째
stack.pop() : 3. 세번째
stack.pop() : 2. 두번째
stack.pop() : 1. 첫번째
stack : []
stack.size() : 0
stack.empty() : true
```
```java
System.out.println("---Stack 전체 데이터 사용---");
		
while (!stack.empty()) {// stack이 비어있지 않으면 사용 가능
 System.out.println("stack.pop() : " + stack.pop());
}
System.out.println("stack.size() : " + stack.size());
System.out.println("stack.empty() : " + stack.empty());
```
```java
---Stack 전체 데이터 사용---
stack.pop() : 4. 네번째
stack.pop() : 3. 세번째
stack.pop() : 2. 두번째
stack.pop() : 1. 첫번째
stack.size() : 0
stack.empty() : true
```

# Queue

**Queue interface**

 - 양쪽이 뚫린 파이프 형태 (접근 통로가 둘)
 - Queue interface 구현 -> LinkedList class
 - 선입 선출 : FIFO (First In First Out)
 - 주요 메서드 : offer(), peek(), poll() (remove() 사용 가능)
 
 ```java
Queue<String> queue = new LinkedList<String>();
System.out.println("queue.isEmpty() : " + queue.isEmpty());

System.out.println("---offer() : 데이터 입력---");
queue.offer("1. 첫번째"); // Queue interface method
queue.offer("2. 두번째"); // Collection, List method
queue.offer("3. 세번째");
queue.offer("4. 네번째"); 

System.out.println("queue : " + queue);
System.out.println("queue.size() : " + queue.size());
System.out.println("queue.isEmpty() : " + queue.isEmpty());

System.out.println("---peek() : 데이터 확인---");

System.out.println("queue.peek() : " + queue.peek());  // 선입 선출 : 처음 데이터부터 확인
System.out.println("queue.peek() : " + queue.peek()); 
System.out.println("queue.peek() : " + queue.peek());

System.out.println("queue : " + queue);
System.out.println("queue.size() : " + queue.size());
System.out.println("queue.isEmpty() : " + queue.isEmpty());

System.out.println("---poll() : 데이터 꺼내기---");
// 단, 데이터가 없을시 null 리턴
System.out.println("queue.poll() : " + queue.poll()); 
System.out.println("queue.poll() : " + queue.poll()); 
System.out.println("queue.poll() : " + queue.poll()); 
System.out.println("queue.poll() : " + queue.poll()); 
System.out.println("queue.poll() : " + queue.poll()); 없으면 null 리턴
//System.out.println("queue.remove() : " + queue.remove()); //NoSuchElementException

System.out.println("queue : " + queue);
System.out.println("queue.size() : " + queue.size());
System.out.println("queue.isEmpty() : " + queue.isEmpty());
 ```
```java
queue.isEmpty() : true
---offer() : 데이터 입력---
queue : [1. 첫번째, 2. 두번째, 3. 세번째, 4. 네번째]
queue.size() : 4
queue.isEmpty() : false
---peek() : 데이터 확인---
queue.peek() : 1. 첫번째
queue.peek() : 1. 첫번째
queue.peek() : 1. 첫번째
queue : [1. 첫번째, 2. 두번째, 3. 세번째, 4. 네번째]
queue.size() : 4
queue.isEmpty() : false
---poll() : 데이터 꺼내기---
queue.poll() : 1. 첫번째
queue.poll() : 2. 두번째
queue.poll() : 3. 세번째
queue.poll() : 4. 네번째
queue : []
queue.size() : 0
queue.isEmpty() : true
```
  ```java
 
 ```
  ```java
 
 ```
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
