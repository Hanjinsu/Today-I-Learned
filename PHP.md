# PHP

## PHP 추상클래스

Abstract Class는 인터페이스의 역할도 하면서 구현체도 갖고 있는 클래스이다.

* 특징
abstract class로 부터 상속받을 때, 명시된 메서드 중 부모 클래스에 정의된 메서드일 경우 반드시 자식 클래스에서 그 구현부를 정의해줘야한다.

해당 메서드들은 반드시 동일한 access지정자를 가져야 한다.

ex) abstract : protected -> child : protected or public

## PHP 정규식

* preg_match : 

 ```php
int preg_match ( string $pattern , string $subject [, array &$matches [, int $flags [, int $offset ]]] )
```
 pattern에 주어진 정규표현식을 subject에서 찾는다.

pattern 탐색 문자열, subject 입력 문자열, matches 검색결과를 채워넣는다, flags 모든 매치에 대한 문자열 시작위치 반환, offset 탐색 시작 위치 지정
