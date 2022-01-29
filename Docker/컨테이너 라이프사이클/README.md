# 도커 컨테이너 라이프사이클
![Capture-5](https://user-images.githubusercontent.com/80312713/151649949-1df26ea1-ea18-4f8d-9978-e7500452955e.png)

## docker 주요 옵션
* -i : 호스트의 표준 입력을 컨테이너와 연결
* -t : tty 할당
* --rm : 컨테이너 실행 종료 후 자동 삭제
* -d : 백그라운드 모드로 실행
* --name hello-world : 컨테이너 이름 지정
* -p 80:80 : 호스트 - 컨테이너간 포트 바인딩
* -v /opt/example:/example : 호스트 - 컨테이너 간 볼륨 바인딩

## 컨테이너 주요 명령어
* 실행중인 컨테이너 상태 확인
  * docker ps
* 전체 컨테이너 상태 확인
  * docker ps -a
* 컨테이너 상세 정보 확인
  * docker inspect [container]
