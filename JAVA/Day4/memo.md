# 인터페이스
## 목적
- 클래스의 다중 상속
- 표준화가 필요할 때
- 객체간 결합도 느슨하게 -> 유지보수를 위해

## 버전 별 차이
<table>
  <th>
    <td> 기존 </td>
    <td> 8버전 이상 </td>
  </th>
  <tr>
    <td> 특징 </td>
    <td> 객체지향 </td>
    <td> 함수적 프로그래밍 지원 </td>
  </tr>
  <tr>
    <td> 사용가능 </td>
    <td> <ul>
           <li> static final </li>
           <li> abstact </li>
         </ul> </td>
    <td> <ul>
            <li> static final </li>
            <li> abstract </li>
            <li> default (구현 가능) </li>
            <li> static (구현가능) </li>
         </ul> </td>
  </tr>
</table>

## default
- interface 는 따로 지정을 안하면 abstract로 지정

## Error 및 Exception
### Error

> Compile Error : Syntax Checking, 언어 규칙
> Runtime Error ; 실행시점 발생하는 에러
>> Runtime 에러 예외 처리
>> 1. handle (try - catch - finally)
>> 2. declare (throws)
