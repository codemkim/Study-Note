# Serializer

## Serializer?
* 사전적 의미는 직렬화이다.
* 파이썬 데이터를 JSON 타입의 데이터로 변환해줌
* Django 프로젝트에서 내가 만든 모델로부터 뽑은 queryset, 즉 모델 인스턴스를 JSON 타입으로 변환

```python
# test/models.py
from django.db import models
class Person(models.Model):
    id = models.IntegerField()
    name = models.CharField()
    phone = models.CharField()
    addr = models.CharField()
    email = models.CharField()
# test/serializers.py
from rest_framework import serializers
from .models import Person

class BasePersonSerializer(serializers.ModelSerializer):
    class Meta:
        model = Person
        fields = ('id', 'name', 'phone', 'addr')

class EmailPersonSerializer(serializers.ModelSerializer):
    class Meta:
        model = Person
        fields = ('id', 'email')
```
* 자신이 만든 특정 모델에서 데이터를 뽑아서 응답으로 보낼텐데, 응답의 형태를 특정 필드로 정의할게라는 의미
    > 즉, 시리얼라이저는 응답으로 보낼 데이터의 형태를 정해주는 하나의 틀
<br>

## Serializer - view 연결
```python
# test/view.py
from rest_framework.response import Response
from rest_framework.decorators import api_view
from .models import Person
from .serializers import BasePersonSerializer, EmailPersonSerializer

@api_view(['GET'])
def PersonAPI(request, id):
    now_person = Person.object.get(id=id)
    serializer = BasePersonSerializer(now_person)
    return Response(serializer.data)
    # id, name, phone, addr 리턴
    
@api_view(['GET'])
def EmailAPI(request, id):
    now_person = Person.object.get(id=id)
    serializer = EmailPersonSerializer(now_person)
    return Response(serializer.data)
    # id, email 리턴
```
* 각 view에서 무언가 데이터를 요청할 때, 각각 원하는 형태로 응답해줘야 한다.<br>
  하지만 모델은 하나니 필요한 데이터만 골라서 보내줘야되고 이러한 역할을 하는것이 시리얼라이저다.
    > 즉, 내가 전송할 데이터(모델 인스턴스)를 시리얼라이저에 넣어 변환시키고 그 데이터를 응답으로 보내주는 것이 <br>
    시리얼라이저 - 뷰 연동 개념이다.
