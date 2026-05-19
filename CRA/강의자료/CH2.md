# UnitTest

## Exception
- 0으로 나누기, Meemory 접근 주소 오류는 기본적인 std::exception이 아님

## Fixture
- fixture로 생성 후 TEST 내 사용시 TEST는 fixture를 상속받음 -> 내부 변수 사용 가능
- setup : 테스트 생성 시 전처리 해야할 것
- teardown : 테스트 종료 후 후처리 해야할 것
