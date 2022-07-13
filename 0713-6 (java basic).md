# Java-study
```java
// Phone 클래스를 상속받아(= extends : 확장해서) Mp3Phone 만들기
class Mp3Phone extends Phone { // Phone에 기본 생성자 없을시 오류
	
	public Mp3Phone() { // 생략 가능
		super();
	}
	
	public Mp3Phone(String phoneNO) {
		super("Mp3Phone", phoneNO); //상위 필드에 저장
	}
	
	public Mp3Phone(String type, String phoneNO) {
		super(type, phoneNO);
	}
	
	//음악 플레이 기능 -------
	public void playMusic() {
		System.out.println(">> 음악 플레이 ~ ");
	}
```
```java
System.out.println("\n---Mp3Phone---");
Mp3Phone mp3ph = new Mp3Phone("010-3333-3333");
mp3ph.view();
mp3ph.call();
mp3ph.receiveCall();
mp3ph.playMusic();
System.out.println(mp3ph.toString());
```
```java
---Mp3Phone---
타입 : Mp3Phone, 전화 번호 : 010-3333-3333
>> 전화 걸기 ~ 
>> 전화 받기 ~ 
>> 음악 플레이 ~ 
com.mystudy.ex02_extends.Mp3Phone@59e84876
```











