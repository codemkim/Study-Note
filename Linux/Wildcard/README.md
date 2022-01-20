# **Wildcard**

## **1. 패턴**
* Filename Matching
  * 많은 commande들이 파일이름을 argument로 사용
  * Wildcard patterns은 여러 개의 파일이름을 쉽게 표현할 수 있게 지원
  * Special Characters : ***, ?, []**
* Wildcard Patterns
  * **?** : Matches any single character
  * -*- : Matches anything(any number of characters)
  * **[..]** : character classes
* Brace({}) 확장
  * 문자열 생성 허용
  * 와일드 카드와 유사하지만 대상 파일 또는 디렉토리가 존재할 필요는 없음
