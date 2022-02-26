# Django Template 문법
* Django의 템플릿 시스템은 템플릿 코드를 해석해서 템플릿 파일을 만듦, 해당 과정을 렌더링이라고 함

# 템플릿 변수
* 사용 형식 : {{ variable }}
* 변수명은 일반 프로그래밍처럼 문자, 수사, 밑줄(_) 사용하여 정의
* 변수 속성 접근도 도트(.) 표현식으로 가능

# 템플릿 필터
* 필터는 파이프(|) 문자 사용
* django는 약 60여가지 필터를 제공하고 있으며, 사용자 정의 필터도 만들 수 있다.

1. {{ name|lower }} # name 변수값의 문자를 소문자로 변경
2. {{ text|escape|linebreaks }} # (필터 체인 가능)  
  > text 변수값 중 특수문자를 이스케이프하고, 그 결과를 스트링에 p 태그 적용
3. {{ bio|truncatewords:30 }} # (인자있는 필터)  
  > bio 변수 값 중 앞에서 30개 단어만 보여주고, 줄바꿈 문자는 모두 없애줌
4. {{ list|join:" // " }}. 
  > list 변수값에 join 적용, 필터 인자의 반칸은 따옴표로 묶어줌
5. {{ value|default:"noting" }}  
  > value 변수값이 False이거나 없는 경우, "noting"으로 보여줌
6. {{ value|lenght }}  
  > value 변수값의 길이 반환(str 이거나 list 인 경우도 가능)
7. {{ value|striptags }}  
  > value 변수 값에서 HTML tag 없애줌
8. {{ value|pluralize }}  
  > 복수 접미사 필터, value 변수값이 1이 아니면 봇구 접미사 s 붙임
9. {{ value|add:2 }}  
  > 더하기 필터 

# 템플릿 


