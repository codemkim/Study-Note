# QuerySet
* Django ORM에서 제공하는 데이터 타입, 데이터베이스에서 전달받은 객체 목록
* 구조는 list와 같지만, Python의 기본 자료구조가 아니기 때문에 자료형 변환을 해줘야 함

# 1. select
* [model].objects.all()  
: 해당 테이블 안에 있는 모든 데이터 조회. QuerySet 타입으로 변환
* [model].objects.get()  
: 하나의 row만 조회(주로 pk칼럼으로 조회), 결과하 1건 이상이면 err 반환, 객체 타입으로 반환
* [model].objects.count()  
: 쿼리 셋에 포함된 데이터 개수를 리턴한다, int 타입으로 반환
* [model].objects.exists()  
: 해당 테이블에 데이터가 있는지 True, False 반환
```python
Model.objects.filter(name="현우").exists()
```
* [model].objects.values()  
: QuerySet의 내용을 딕셔너리 형태로 반환, 인자값에 특정 필드 입력 시 입력한 필드에 대한 값을 반환
* [model].objects.values_list()  
: values()와 같으나 QuerySet의 내용을 리스트 타입으로 반환
* [model].objects.order_by()  
: 특정 필드를 기준으로 정렬을 할 때 사용. 필드명 앞에 -가 붙으면 내립차순을 의미
```python
# name 필드를 기준으로 내림차순 정렬, 두번째 기준은 id 필드
Model.objects.order_by('-name', 'id')
```
* [model].objects.first() / last()  
: 쿼리셋 결과 중 가장 첫번째 / 마지막 row만 조회할 때 사용, 객체 타입 반환
* [model].objects.aggregate()  
: django의 집계함수 모듈(Avg, Max, Count, Sum 등)을 사용할 때 사용하는 메소드, 딕셔너리 타입으로 반환
```python
# name 필드를 기준으로 내림차순 정렬, 두번째 기준은 id 필드
Model.objects.order_by('-name', 'id')
```


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
* (특정컬럼명)__gt  
: 특정 값 보다 큰 데이터만 조회 ( greater than의 약자 )
* (특정컬럼명)__lt  
: 특정 값 보다 작은 데이터만 조회 ( less than의 약자 )
* (특정컬럼명)__isnull.  
: True로 지정 시 특정 필드 값이 null인 것만 조회
* (특정컬럼명)__in  
: 리스트 안에 지정한 문자열들 중에 하나라도 포함된 데이터를 찾을 대 사용 ( 단, 정확히 일치해야 됨 )
* (특정컬럼명)__year, __month, __day, __date  
: date 타입의 필드에서 특정 년,월,일,날짜의 데이터를 찾을 때 

## + AND / OR
> filter() 메소드 사용 시 두개 이상의 조건을 AND 또는 OR을 이용하여 표현할 수 있음

* AND 조건 : 두 개 이상의 쿼리 셋을 ' & '로 연결
* OR 조건 : 두 개 이상의 쿼리 셋을 ' | '로 연결
```python
# AND 조건
Model.objects.filter(id__gt=6) & Model.objects.filter(name__contains = "현우")

# OR 조건
Model.objects.filter(id__gt=6) | Model.objects.filter(name__contains = "현우")
```
* django의 Q 객체로도 표현 가능
```python
from django.db.models import Q

# Q를 활용한 AND 조건
Model.objects.filter(Q(id__gt=6) & Q(name__contains = "현우"))

# Q를 활용한 OR 조건
Model.objects.filter(Q(id__gt=6) | Q(name__contains = "현우"))
```


