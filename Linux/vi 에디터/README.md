# **vi 에디터**

## **1. 구조**
![다운로드 (1)](https://user-images.githubusercontent.com/80312713/150082913-1e5061df-9691-4eac-a13c-55114616a58d.png)
<br>

## **2. 단축키**
![242DBF47583A6FB106](https://user-images.githubusercontent.com/80312713/150083077-a7806bf5-64d4-451f-8671-5a94f23f40d0.jpeg)
* 자주쓰는 단축키
  * command mode
    * i 해당위치에서 입력
    * o 한줄띄고 입력 
  <br>
  
  * ex mode
    * :e! 편집취소
    * :w 저장
    * :wq 저장하고 나가기
    * :w <newfile> 새이름으로 저장
    * :q vi 편집기 취소후 종료
    * :q! 변경사항 취소후 종료
    * :r <filename> 편집중인 파일에 다른파일을 끼워넣기
    * :%s /찾을문자열/변경할문자열/g 찾아서 바꾸기 
 

<br>

## **3. vim 에디터 관련 사이트**
* https://www.vim.org/

<br>

## **4. 그외**
* mac에서 brew 설치하기
  * 터미널에서 아래 명령어 입력 
    * /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    * vi ~/.zshrc
    * i 입력으로 인서트모드로 들어가기
    * export PATH=/opt/homebrew/bin:$PATH 입력
    * esc 입력으로 커맨드모드로 돌아가기
    * :wq  입력으로 저장하고 나오기
   
