### 초기화
객체 초기화 시 ex) Node a(1,2); 는 준비된 구조에서만 동작하므로 중괄호, 일반적인 객체 초기화 권장 

### 캐스팅
static_cast : 형 변환 가능한 타입 끼리만 변환 가능하도록 체크
암묵적 형 변환은 X

### 동적할당
malloc 사용 시 delete 필수
smart_pointer는 직접 delete 불필요
