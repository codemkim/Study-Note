# **AWS Lambda**

<br>

## **1. 특징**
* 어떠한 이벤트가 발생했을 때 특정 함수를 동작할 수 있도록 해주는 서비스 
* 별도의 웹 서버처럼 운영할 수도 있다.
* 클라이언트의 요청을 처리한 뒤에 그 처리 내역을 데이터베이스 or AWS 자체 로그로 저장하거나 관리할 수 있다.
* 아마존 웹 서비스가 제공하는 별도의 플랫폼에서 손쉽게 서버를 구축해서 데이터를 저장하고, 처리하고, 출력할 수 있다는 장점이 있다.

<br>

## **2. 구성도**
* **플레이어(클리아이언트)** > **API 게이트웨이** > **AWS 람다** > **DB**
    > 클라이언트가 우리의 서버에 접속하면, 먼저 API 게이트웨이를 거치게 되고, 이후에 AWS 람다가 실제로 클라이언트의 요청을 처리하고 그결과를 반환

<br>

## **3. 기본 AWS Lambda 구현**
<img width="704" alt="323" src="https://user-images.githubusercontent.com/80312713/149885730-ff30387c-ec88-454b-a470-50599e1deedc.png"><br>
* API 엔드포인트 <br>
  * https://a8w2o14f94.execute-api.us-east-2.amazonaws.com/default/hello_lambda_python

<br>

## *AWS Lambda를 활용한 게시판 서버 API 만들기(진행중)*
* AWS Lambda 함수 구현
* API Gateway GET,POST 리소스 및 메서드 구현
* mongoDB 데이타베이스 활용
* ~
