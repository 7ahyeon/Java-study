# String, StringBuffer, StringBuilder

**String**
- 불변 (immutable)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 부적합
- thread-safe : 멀티 쓰레드 환경에서의 안정성
- 문자열 연산이 적고 멀티 쓰레드일 경우

**StringBuffer**
- 가변 (mutable)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 적합
- thread-safe : 멀티 쓰레드 환경에서의 안정성 (동기화 키워드 제공)
- 문자열 연산이 많고 멀티 쓰레드일 경우

**StringBuilder**
- 가변 (mutable)
- 동일 객체 내 추가, 수정, 삭제 다수 발생시 적합
- 단일 쓰레드 환경에서의 성능 뛰어남
- thread-safe X : 멀티 쓰레드 환경 부적합 (동기화 키워드 제공X)
- 문자열 연산이 많고 단일 쓰레드거나 동기화를 고려하지 않아도 되는 경우

