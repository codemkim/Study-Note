# Ingress
> 클러스터 내의 서비스에 대한 외부 접근을 관리하는 API 오브젝트이며,<br>
> 일반적으로 HTTP를 관리하고, 부하 분산, SSL 종료, 명칭 기반의 가상 호스팅 제공
<br>

## 사전 용어 및 전제 조건
> **인그레스 컨트롤러**가 있어야 인그레스를 충족할 수 있다. 인그레스 리소스만 생성하면 의미없다.
* 노드 : 클러스터의 일부이며, 쿠버네티스에 속한 워커 머신
* 클러스터 : 쿠버네티스에서 관리되는 컨테이너화 된 애플리케이션을 실행하는 노드 집합
* 에지 라우터 : 클러스터에 방화벽 정책을 적용하는 라우터
* 클러스터 네트워크 : 쿠버네티스 네트워킹 모델에 따라 클러스터 내부에서 통신을 용이하게 하는 논리적 또는 물리적 링크 집합
* 서비스 : 레이블 셀렉터를 사용해서 파드 집합을 식별하는 쿠버네티스 서비스.
<br>

## 인그레스란?
* 인그레스는 클러스터 외부에서 클러스터 내부 서비스로 HTTP와 HTTPS 경로를 노출하며,<br>
* 트래픽 라우팅은 인그레스 리소스에 정의된 규칙에 의해 컨트롤 된다.
  <img width="432" alt="Screenshot at Feb 06 14-38-08" src="https://user-images.githubusercontent.com/80312713/152669033-33dc1581-9bd1-4374-a01c-5dbb58567e13.png">
  > 인그레스는 외부에서 서비스로 접속이 가능한 URL, 로드 밸런스 트래픽, SSL/TLS 종료<br>
  > 그리고 이름-기반의 가상 호스팅을 제공하도록 구성할 수 있다. **인그레스 컨트롤러**는 일반<br>
  > 적으로 로드 밸런서를 사용해서 인그레스를 수행할 책임이 있으며, 트래픽을 처리하는데 도움이 되도록<br>
  > 에지 라우터 또는 추가 프런트 엔드를 구성할 수도 있다.

## 인그레스 규칙
> 각 HTTP 규칙에는 다음의 정보가 포함된다.
  * 선택적 호스트
  * 경로목록
  * 벡엔드 목록