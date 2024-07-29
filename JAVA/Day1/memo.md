# JAVA

## 식별자(Indetifier)
### 1. 종류
- 변수, 클래스, 인터페이스, 메서드 등
- Syntax : 클래스에는 대문자로 시작, Camel형식

## 소스파일 구성

### 1. Package 등록
```java
package 패키지
```


### 1. 타 패키지 클래스 가져오기
```java
import java.lang.* : 자동 import
import 패키지.클래스
```
<hr/>
JAVASE
#### 1. Standalone Application : Serverless App

```java
public static void main(~){
// entry point 이면서 end point
```


JAVA Net와 Java IO API로 채팅 Application (Client / Service Application)


## 3.값 유형 : 문자, 숫자, 논리값
Scalar 타입 => primitive data type, 8개의 유형 지원, = 연산자와 함께 사용
Composite 타입 => reference data type, (배열, Collection 타입 (자료구조 + 알고리즘), class , interface) 객체로 취급하는 타입
.연산자와 함께 사용
-> Referencec Type은 선언, 생성, 초기화 단계가 필요

```java
<1>
String s ;
s = new String("java") : 생성과 초기화, heap 메모리에 생성

<2>
String t = "hello"; : 선언과 생성 초기화, String pool 메모리 영역에 생성됨
```

### promotion / casting
- promotion : 작은 크기의 값을 큰 크기의 타입에 할당할 때 자동으로 작은 크기 타입으로 변경
- casting : 큰 크기의 값을 작은 크기의 타입에 할당할 때 명시적으로 타입을 변경
- > casting은 서로 변환 시 범주가 다르면 크기와 상관없이 casting 필요
  > bool은 숫자와 호환 X : casting, promotion 둘 다 불가


### 1. 자료형
- 논리 자료형 : boolean(1byte 할당 : 1byte단위로 할당되기 때문에 1bit 불가)
- 정수 자료형 : byte(1B), short(2B), int(def, 4B), long(8B), char(2B)
- 실수 자료형 : 부동소수점형식으로 저장, float(4B), double(def, 8B)

-> byte도 맨 첫자리는 sign bit
입력 시 해당 자료형 범위에 값이 들어가는지를 확인하고 컴파일 전 오류 출력
정수 직접 입력 literal로 입력 시 4byte가 넘어가면 오류 -> 4byte 넘어가면 뒤에 l/L 붙임

## 변수 선언 위치
- 클래스 내부 : 멤버 필드 (init x 시 자동으로 컴파일 시 초기화)
- 메서드 내부 : 로컬 변수 (사용 전 초기화 필요)

!boolean타입의 변수에 정수 불가!

## 부동소수점
실수 자료형 : 부동소수점 형식
정수부.소수부 => (부호) X (가수부) X (지수부)


## jAVA in
- 기본 System.in에서 제공하는 in은 1byte 씩 가능
- new BufferReader(new InputStreamReader(System.In))으로 새 객체 생성후
- readLine()을 사용하여 in
- > 이 때 문제가 buffer는 OS 단에서 제어하므로 JRE 범주를 넘어섬 -> 컴파일 에러 확인 불가
  > 예외 처리 반드시 필요
  
-> Util 내 Scanner의 등장으로 적은 코드로 예외처리까지 가능

