# 객체 지향
## 특징
- 객체들의 분리와 결합이 용이

## 특성
> 캡슐화 : 복잡성을 숨기고 필요한 요소만 노출 : private, public 등
> 상속 : 부모클래스로부터 private멤버 및 생성자를 제외한 모든 멤버와 메서드 상속
>        기본적으로 java.lang.object를 상속 받음(Root 클래스)
>        부모클래스는 공통 속성과 메서드 정의 : 일반화, 추상화
> 다형성 : 다양한 형태를 가질 수 있음
>          overload, override로 구현

## 클래스
### 선언
> AccessModifier (public (default))    
> [Modifier] (final, abstract)      
> class         
> 클래스 이름        
> [extends 부모클래스] : 클래스 간 상속은 단일 상속만 지원         
> { ... }   

<hr/>
### 멤버필드
> 인스턴스 필드 (객체 생성 시 heap 메모리에 생성 후 초기화되고 객체로 access)   
> static 필드 (객체 생성없이 access 가능, 클래스이름으로 access, 모든 객체가 하나의 변수 값을 공유하고자 할 때 : 전역변수)    
> 상수 (final 선언 및 명시적 초기화가 필요)    
