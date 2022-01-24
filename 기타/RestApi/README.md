# REST API
> Repersentational State Transfer
<br>

## REST 의 구성
*  자원(Resource) - URL
*  행위(Verv) - HTTP METHOD
*  표현(Representations)
<br>

## REST 의 특징
* Uniform(유니폼 인터페이스)
> 유니폼 인터페이스는 URL로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일
* Stateless(무상태성)
> 작업을 위한 상태정볼를 따로 저장하고 관리하지 않고 api 서버에 들어오는 요청만을 단순히 처리<br>
> 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해짐
* Cacheable(캐시 기능)
> HTTP라는 기존 웹 표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존인프라를 그대로 활용 가능
* Self-descriptiveness(자체 표현 구조)
> REST API 메시지만 보고도 이를 쉽게 이해 할 수 있는 자체 표현 구조
* Client - Server 구조
> REST 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션,로그인정보)등을 직접 관리하는 구조
* 계층형 구조
> 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성 마련<br>
> Proxy, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 함.
<br>

## REST API 디자인 가이드
* URL은 정보의 자원을 표현해야 한다.
* 자원에 대한 행위는 HTTP METHOMD(GET, POST, PUT, DELETE)로 표현
<br>

## HTTP Method(CRUD)
* POST
> 해당 url를 요청하면 리소스를 생성
* GET
> 해당 리소스를 조회, 도큐먼트에 대한 자세한 정보도 가져옴
* PUT
> 해당 리소스를 수정
* DELETE
> 해당 리소스를 삭제
