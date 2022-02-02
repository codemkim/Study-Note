# Serializer

## Serializer?
* 사전적 의미는 직렬화이다.
* 파이썬 데이터를 JSON 타입의 데이터로 변환해줌
* Django 프로젝트에서 내가 만든 모델로부터 뽑은 queryset, 즉 모델 인스턴스를 JSON 타입으로 변환


## 사용 예
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
