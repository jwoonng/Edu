# 1. 단위 전략

## 1.1 Template Method

## 1.2 Strategy Method
특징 : 컨테이너와 할당기가 완전히 분리되어 있음
장점 : 타 컨테이너에서도 활용 가능

- [x] 사용하지 않는 이유
- Allocate / deallocate 가 가상함수
     > 가상함수 테이블의 메모리 오버헤드
     > 가상함수 호출 시 성능저하

## 1.3 단위 전략( Policy Base Design )
클래스가 사용하는 정책 클래스를 교체하는 2가지 방법
### 1.3.1 인터페이스 기반 교체 (Strategy Method)
- 인터페이스가 있다 = 모두 가상함수다
- 반복적으로 호출되는 함수는 성능저하가 있다.

### 1.3.2 template 인자로 교체(Policy Base Design)
특징 : 모든 정책은 인터페이스로 설계되지 않고 문서화 되어야 함
장점 : 가상함수가 아닌 인라인으로 치환 가능하여 빠르다




* Malloc
* Allocate / deallocate
* Template<typename T>
* Inline : 해당 기능의 기계어 코드를 호출
