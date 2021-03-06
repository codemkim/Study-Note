# User Model
* `Django`는 백엔드에서 꽤 중요한 부분을 차지하고 있는 권한과 인증에 대해 구현이 되어 있으며,  
  이때 `User Model`이 사용자들의 데이터를 저장한다.

## 프록시 모델
* 테이블 추가, 변경 없이 단순히 상속만 하는 방식
* 정렬순서나 필요한 메소드만 추가하기 위해 사용
* 기존의 User Model에 추가적인 사용자 정보를 저장할 필요가 없을 때 사용하는 가장 간단한 방법
* 기본 모델

## 일대일 연결(One-to-One)
* 모델(테이블)을 추가하여 기존 User Model과 일대일로 연결시켜서 사용자에 대한 정보를 저장
* Django의 인증 시스템을 그대로 활용하고 로그인, 권한 부여 등과 상관이 없는 사용자 데이터를  
  저장하고자 할 때 사용하는 가장 간단한 방법
  
## AbstractUser 모델 
* `AbstractUser Model`을 상속한 `User Model`을 새로 정의하여 사용(settings.py 수정필요)
* 이 기법의 사용 여부는 프로젝트 시작 전에 하는것이 좋음
* 기존의 `User Model`을 그대로 사용하므로 기본 로그인 인증 처리 부분은 `Django`의 것을 이용하면서  
  몇몇 `사용자 정의 필드`를 `추가`할 때 유리함
  
