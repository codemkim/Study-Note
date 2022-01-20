
# **다중 명령어 처리**

## 1. 특징
* 하나의 command line에 여러 개의 명령을 실행할 수 있음
  * command1; command2
  * command && command
  * command || command
<br>
* example
  * date; ls
  * ls /user/bin/id && id guru
  * ls file.txt || touch file.txt
