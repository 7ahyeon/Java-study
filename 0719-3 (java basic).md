# Generic

**Generic**
- 컬렉션이 어떤 객체들로 이루어졌는지 표시하는 객체타입을 의미
- 제네릭 형태 : <객체자료형>, <>
- API -> <T> : 객체자료형, <E> : 하나의 요소(즉 객체 하나를 의미)
- Map형식 : <K, V> K는 key(키), V는 value(값)

**대표문자 wildcard**
1. <?> : 모든 타입(객체) 자료형에 대한 대표문자를 의미
2. <? extends 자료형> : 자료형을 상속받은 자녀(sub) 클래스 타입 사용
3. <? super 자료형> : 자료형의 부모(super) 타입 사용           

**Collection**
- 객체들을 모아 놓은 것(객체를 모아서 관리)
- Collection<E> => Set<E>, List<E>, Queue<E>, Map<K,V>