# Socket
<br>

## WebSocket vs socket.io
* 웹소켓은 양방향 소통을 위한 **프로토콜**
> 프로토콜? 서로 다른 컴퓨터끼리 소통하기 위한 약속
* socket.io는 양방향 통신을 하기 위해 웹소켓 기술을 활용하는 **라이브러리**
<br>

## WebSocket
* HTML5 웹 표준 기술
* 매우 빠르게 작동하며 통신할 때 아주 적은 데이터를 이용한
* 이벤트를 단순히 듣고, 보내는 것만 가능함
<br>

## Socket.io
* 표준 기술이 아니며, 라이브러리임
* 소켓 연결 실패 시 fallback을 통해 다른 방식으로 알아서 해당 클라이언트와 연결을 시도함
* 방 개념을 이용해 일부 클라이언트에게만 데이터를 전송하는 브로드캐스팅이 가능함
<br>

## 상황에 맞는 적용은?
* 서버에서 연결된 소켓(이용자)들을 세밀하게 관리해야하는 서비스인 경우에는 브로드캐스팅 기능이 있는<br> **socket.io**를 사용하는게 유지 보수 측면에서 이점이 많음
* 가상화페 거래소같이 데이터 전송이 많은 경우에는 빠르고 비용이 적은 표준 **웹소켓**을 이용하는게 바람직함.
