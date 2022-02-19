
# Celery
* `Celery`는 Python `동시성 프로그래밍`에서 가장 많이 사용하는 방법 중 하나이며  
  분산 메시지 전달을 기반으로 동작하는 `비동기 작업 큐(Asynchronous Task/Job Queue)`이다
* `Worker`라고도 칭하며, 웹 서비스에서 Back단의 작업을 처리하는 별도의 프레임이며, 사용자에게 즉각적인 반응을  
  보여줄 필요가 없는 작업들로 인해 사용자가 느끼는 `Delay를 최소화` 하기 위해 사용된다.
> `Celery`는 메시지를 전달하는 역할(`Publisher`)과 메시지를 Massage Broker에서 가져와  
  작업을 수행하는 `Worker`의 역할을 담당
 
<br>

# 왜 Celery 인가?
* `Django` 등으로 API 서버를 개발하고 운영하면서 사용자 요청에 포함될 필요가 없는 불필요한 과정이나  
  매우 무거운 쿼리 실행을 포함하는 경우가 있으며 해당 작업은  
  `회원 가입 축하 이메일 발송`, `주문 내역 엑셀 다운로드` 등이 해당된다.  
* 이 API에 포함된 외부 연동이나 무거운 작업들은 `Celery Task`로 정의해서 `Broker(RabbitMQ)`와  
  `Consumer(Celery Worker)`를 이용해 `Async`하게 처리함으로써 사용자에게 가능한 빠른 응답을 제공한다.
  
<br>

# Celery 동작 구조 
![image](https://user-images.githubusercontent.com/80312713/154784454-93c2f246-c1c5-455f-9c8a-e5ca42ba5d0d.png)


