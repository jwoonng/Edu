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
>> AccessModifier (public (default))    
>> [Modifier] (final, abstract)      
>> class         
>> 클래스 이름        
>> [extends 부모클래스] : 클래스 간 상속은 단일 상속만 지원         
>> { ... }   

   
### 멤버필드    
> 인스턴스 필드 (객체 생성 시 heap 메모리에 생성 후 초기화되고 객체로 access)   
> static 필드 (객체 생성없이 access 가능, 클래스이름으로 access, 모든 객체가 하나의 변수 값을 공유하고자 할 때 : 전역변수)    
> 상수 (final 선언 및 명시적 초기화가 필요)    
>   
>> AccessModifier (public, pritected, (default), private)    
>> [Modifier] (final, static, transient)    
>> Type (primitive / reference data type)    
>> '='   
>> Value

### 멤버 메서드
> static 메서드 : static 필드에 대해 기능, 변경 가능   
> final 메서드 : 상속 시 override 금지   
> abstract 메서드 : body가 없는 메서드, 반드시 override 강제   
> native 메서드 : 외부 라이브러리를 로드 System.load() 시키는 메서드   
> syncronized 메서드 : 스레드 클래스의 메서드에서만 사용, 공유자원을 스레드 객체들이 sequential하게 호출해서 수행   
>   
>> AccessModifier (public, protected, (defualt), private)   
>> [Modifier] (static ~ syncronized)   
>> Type (primitive, reference data type, void)   
>> 메서드 이름   
>> ([매게변수 리스트])   
>> [throws 예외클래스]   
>> { ... }

## 기타
- lombk 라이브러리에서 자동으로 setter getter 생성

## overload
- 동일한 기능에 대해 파라미터를 다르게 전달
- 메서드 이름 외 나머지는 다르게 설정 가능
- 대신 파라미터의 순서, 타입, 개수 중 하나는 다르게 정의 -> 이걸로 구분

## override
- 동일하게 선언하고 body만 변경 가능
- 상속받은 override는 1번만 간ㅡㅇ
- AccessModifier 변경 시 더 유효범위가 넘은 것으로 선언
- override에서 throws 사용 시 부모 클래스의 예외클래스보다 더 상위 예외 클래스의 throws는 불가

## final
- final 클래스 : 상속 불가
- fianl 메서드 : override 불가
 
## abstract
- abstact 메서드가 포함된 클래스는 instance 생성 불가
  -> 클래스에 abstract 선언 필요

## static
- static으로 정의된 메서드 내에서는 외부 non-static은 호출 불가

## inner class
- outer class의 private 멤버까지 access 가능
- inner class객체 생성 시 : new 외부클래스(~).new 내부클래스(~)
- inner class 내 멤버/메서드가 static 이면 자동으로 클래스에 static 선언

## 익명 클래스
- 생성과 동시에 구현

## java string
- ==는 주소를 확인하는 것으로 eqaul을 통해 확인
