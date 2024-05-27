# A. 생성자
1. 기반 / 파생 생성자 중 우선 부르는 순위 : 파생 생성자 호출 -> 기반 생성자 호출 -> 기반 생성자 코드 실행 -> 파생 생성자 코드 실행 // 소멸은 파생 먼저 소멸 후 기반 소멸
     >> 결과를 보고 예측 X

2. 컴파일러는 개발자가 작성하지 않은 기반 생성자를 자동으로 작성해 줌 (default 생성자) / 소멸자는 소멸자를 호출 (https://daklee.tistory.com/entry/항목-5-C가-자동으로-만들고-호출하는-함수들)
3. Private, public, protected 생성자
- 생성자가 public : 모두 가능
- 생성자가 private : 부를 수 없음
- 생성자가 protected : 기반 직접 부르기 X, 생성 파생자를 통해 부르기 O
      >> 의도 : 추상개념의 클래스 화

- 순수가상함수 : https://blockdmask.tistory.com/277

# B. Upcasing
1. 파생클래스의 주소를 기반 클래스에 담을 수 있다. Ex) Dog d1;  Animal* p = &d1; // 가능
      -> 메모리 구조 상 파생 클래스 가장 상단 메모리에는 기반 객체에 할당된 메모리가 위치 -> 파생 객체 가장 상단 메모리 = 기반 객체 가장 상단 메모리
2. 기반 객체 포인터로 파생 객체의 멤버 접근 불가. Ex) p->color // 불가
3. 기반 객체 포인터로 파생 객체 멤버를 접근하고 싶으면 캐스팅을 하면 된다. Ex) static_cast<Dog*>(p)->color // 가능

4. Casting
- C++은 컴파일 시간에 타입을 체크하므로, 파생 객체의 고유 멤버에 접근 불가 (static type check)
      >> static 의미 : 컴파일 시간에 정함
      >> dynamic 의미 : 실행 시간에 정함

- Dynamic Cast : 안 쓰는게 좋음
      >> 실행 시간에 정하려면 무슨 탑인지 미리 정의가 되어 있어야 함. -> C++에선 가상함수 테이블에 정함
      >> 가상함수 테이블에 정의가 되려면 가상함수가 하나 이상 정의가 되어 있어야함

- () 와 static_cast차이
      >> () : 타입과 상관없이 에러가 나오지 않음 : 안 쓰는게 좋음
      >> Static_cast : 타입 정의와 관련된 에러를 표시

# 5. 활용
- 파생객체 활용 : 파생객체(동일 기반 클래스)만 가능
- 기반객체 활용 : 기반객체에 파생된 모든 파생객체까지 활용 가능 


# C. 가상함수
1. 함수 바인딩
- Static binding : 컴파일러는 포인터의 객체가 기반인지 파생인지 알 수 없다. 그래서 컴파일러는 선언 시 정의된 타입으로 포인터의 객체를 정의한다.
      >> 논리적이지 않지만 빠름 (C,C++, C#)
- Dynamic binding : 컴파일러가 포인터의 메모리를 조사하여 타입을 판단. 
      >> 논리적이지만 느림 (JAVA, Python, Swift 등)
      >> C/C++/C# 의 가상함수(virtual) 사용 시 dynamic binding 사용
      >> JAVA 는 Interface 와 abstract 명시적으로 구분하지만 C/C++ 는 순수 가상함수만 사용
            >> C/C++는 순수가상함수만 있으면 인터페이스, 순수가상함수 + 다른거가 있으면 추상클래스

2. 소멸자
- delete p 와 p->소멸자 는 동일한 기능
- 기반 포인터 = 파생 객채 주소 시 delete 포인터 할 경우 기반 객체만 소멸 : 메모리 누수 발생!
- Virtual 함수를 써서 파생 객체 까지 한 번에 소멸 필요

3. 기타
- 동일함수의 가상함수 재 정의 시 virtual 키워드 생략가능
- 가상함수 override 시 오타는 새 함수로 인식
       >> override 키워드 도입으로 override로 인한 버그 해결
       EX) virtual void foo() override {} 


* Override 과 Overloading
- Link : https://woo0doo.tistory.com/15

* 컴파일러가 만든 어셈블리 코드를 확인하면 모든 코드가 어떻게 동작하는 지 더 손쉽게 알 수 있음
- Link : https://godbolt.org


# D. 추상클래스
1. 정의 : 순수 가상함수가 한 개 이상 있는 클래스
2. 특징 : 객체를 만들 수 없다.
3. 의도 : 파생클래스에 이 함수는 만들어야 한다고 제시
4. 파생에서 추상클래스 정의
- 추상클래스에 순수 가상함수 draw()가 있을 시
      >> 파생클래스에서  draw() 구현 X : 파생클래스도 추상클래스
      >> 파생클래스에서 draw() 구현 O : 파생클래스는 Concreate클래스

* 순수가상함수
- 구현부는 없고, ‘=0’ 으로 표기
       EX) virtual void draw() = 0;

* OCP(open close principle : 개방 폐쇄 원칙) 
- 새로운 모듈, 클래스가 추가 되어도 기존 코드는 수정이 되지 않도록 해야한다.

* SOLID 원칙!
- 객채 지향 프로그래밍애서 반드시 지켜야하는 5가지 원칙
- SRP, OCP, LSP, ISP, DIP


*  강한 결합 (tightly coupling) 및 약한 결합 (
- 강한 결합 : 하나의 클래스가 직접 다른 클래스의 이름을 사용 
       >> Ex) ues_camera(Camera A)

- 약한 결합 : 하나의 클래스가 Interface 클래스의 이름을 사용
      >> Ex) use_camera(ICamera A)


* Struct, Class 차이(c++에서)
- Struct : 접근지정자 생략 시  기본 public
- Class : 접근지정자 생략 시  기본 private
- 위 기본 접근지정자를 제외한 나머지 완벽히 동일하므로 상속도 가능
