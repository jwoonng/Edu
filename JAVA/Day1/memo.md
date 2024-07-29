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

### 1. 자료형
- 논리 자료형 : boolean(1byte 할당 : 1byte단위로 할당되기 때문에 1bit 불가)
- 정수 자료형 : byte(1B), short(2B), int(def, 4B), long(8B), char(2B)
- 실수 자료형 : 부동소수점형식으로 저장, float(4B), double(def, 8B)
