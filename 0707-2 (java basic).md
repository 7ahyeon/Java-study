# Java-study

**method overloading**
- 같은 클래스 내에서 같은 이름의 메소드를 축적하는 것
- parameter의 개수, 타입 등을 다르게 함

```java
static void printData(int arr[]) {
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i] + " ");
	}
	System.out.println();
}
	
// method overloading
static void printData(String name, int arr[]) {
	System.out.print(name + " : ");
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i] + " ");
	}
	System.out.println();
}
```





