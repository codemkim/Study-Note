# QuerySet
* Django ORM에서 제공하는 데이터 타입, 데이터베이스에서 전달받은 객체 목록
* 구조는 list와 같지만, Python의 기본 자료구조가 아니기 때문에 자료형 변환을 해줘야 함

# select
* [model].objects.all()  
: 해당 테이블 안에 있는 모든 데이터 조회. QuerySet 타입으로 변환
* [model].objects.get()  
: 하나의 row만 조회(주로 pk칼럼으로 조회), 결과하 1건 이상이면 err 반환, 객체 타입으로 반환
* [model].objects.filter(). 
: 특정 조건에 맞는 row만 조회하고 싶을 때 사용한다. QuerySet 타입으로 반환.
* [model].objects.exclude()  
: 특정 조건을 제외한 데이터만 조회하고 싶을 때 사용, QuerySet 타입으로 반환

## + Lookup filter
> filter(), exclude() 메소드에서 사용 가능한 내장 모듈로, 필드별 구체적인 값에 대한 비교를 가능하게 함  
* (특정컬럼명)__contains  
: 특정 문자가 포함된 것을 찾을 때 사용 ( 대소문자 구분 )
* (특정컬럼명)__icontains  
: 특정 문자가 포함된 것을 찾을 때 사용 ( 대소문자 구분 X )
* (특정컬럼명)__startswith  
: 특정 문자로 시작하는 것을 찾을 때 사용
* (특정컬럼명)__endswith  
: 특정 문자로 끝나는 것을 찾을 때 사용
