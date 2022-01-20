
# **다중 명령어 처리**

## 1. 특징
* 하나의 command line에 여러 개의 명령을 실행할 수 있음
  * command1; command2 
  * command && command : 앞에 있는 커맨드가 성공적으로 실행되면 뒤에 커맨드도 실행해줌. **조건문**이랑 비슷함
  * command || command : 앞에 있는 커맨드가 실패하면 뒤에 있는 커맨드를 실행함. **eles** 랑 비슷함 
<br>

* example
  * date; ls
  * ls /user/bin/id && id guru
  * ls file.txt || touch file.txt
