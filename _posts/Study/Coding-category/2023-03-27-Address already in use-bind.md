---
layout: single
title: "Address already in use - bind(2): 작동중인 프로세스 강제종료"
categories: 
    - Error 
    - Coding
toc: true
---

## 에러코드
Address already in use - bind(2) (Errno::EADDRINUSE)<br><br>


## 발생원인
이전에 로컬에서 확인한 사이트를 종료하지 않고 비주얼스튜디오코드를 종료한 경우에 발생.
지킬 블로그를 로컬에서 확인한 후 ctrl+c로 종료하지 않은 상태에서 비주얼스튜디오코드를 종료했다 다시 서버를 실행하면 발생했다.<br><br> 


## 해결방법
(1) lsof -wni 실행
``` 
lsof -wni
``` 
<br>


(2) 종료할 프로세스의 PID를 찾는다
``` 
COMMAND     PID        USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
ruby      24913     username   23u  IPv4 0xa9c739662b1f6207      0t0  TCP 127.0.0.1:35729->127.0.0.1:56576 (ESTABLISHED)
``` 
<br>


(3) 강제종료
``` 
kill -9 [PID 번호]
``` 
예: (2)에서 확인한 PID 값이 24913이므로, 'kill -9 24913'을 입력 후 엔터
<br>