# helloworld230523
# 20233116 박진우 *과제 2*

|명령어||||
|-----|:---|---:|:---:|
|**top**|**ps**|**jobs**|**kill**|

-----------------
 + **top**
      + 시스템의 상태를 빠르게 파악(CPU, Memory, Process)
      + interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여준다.

```bash
top -b #batch 모드, 순간의 정보
top -n #top 실행 주기 설정(반복 횟수)
```
```bash
top -b -n 1
```
![리눅스 top -b -n 1](https://github.com/felltah/helloworld230523/assets/126939612/fc090729-388b-4bb8-b665-d5c5dbd87f99)
+ top 실행 후
  + shift + p : CPU 사용률 내림차순
  + shit + m : 메모리 사용률 내림차순
  + shift + t : 프로세스가 돌아가고 있는 시간 순
  + k : kill. k 입력 후 PID 번호 작성. signal은 9
  + f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
  + a : 메모리 사용량에 따라 정렬
  + b : Batch 모드로 작동
  + 1 : CPU Core별로 사용량 보여줌
------------------
+ **ps**
  + 현재 실핸중인 프로세스 목록과 상태 보여줌.
  + 사용법: 
  ```bash
  ps #[옵션]
  ```
![ps 옵션](https://github.com/felltah/helloworld230523/assets/126939612/7c891c7e-ecb3-4232-9016-1b19bc3cc41f)

옵션을 주었을 때 System V, BSD, GNU에 따라 결과가 다르게 나타남.  **옵션을 정확히 주는 것이 중요하다**

옵션은 특정 프로세스를 확인할때 grep과 자주 함께 쓰인다.
```bash
ps -ef | grep 'root'
```
![ps -ef](https://github.com/felltah/helloworld230523/assets/126939612/6391b6e0-3091-497e-bec4-1cefc9976b69)

-------------------
+ **jobs**
   + 백그라운드에서 실행되고있는 프로세스 조회
   + 사용법: 
  ```bash
  jobs #[옵션] #[번호]
  ```
 
 + 옵션
     + -l : 프로세스 그룹 ID를 state 필드 앞에 출력
     + -n : 프로세스 그룹 중에 대표 프로세스 ID를 출력
     + -p : 각 프로세스 ID에 대해 한 행씩 출력
     + command : 지정한 명령어를 실행
--------------
+ **kill**
    + 프로세스에 특정한 signal을 보내는 명령어이다.
    + 일반적으로 종료되지 않는 프로세스를 종료시킬 때 많이 사용한다.
    + 
    ```bash
    kill #[PID] #각 프로세스는 유일한 프로세스 번호 PID를 갖는다.
    ```
    
+ s 옵션으로 시그널을 지정하지 않으면 기본 시그널 값이 정상종료된다. (SIGTERM,15)
+ 프로세스를 안전하게 종료하기 위해서는 "kill -9 pid", "kill -SIGKILL pid" 형태로 프로세스 강제 종료를 권장하지 않는다. (데이터 유실 위험)
+ 일반적으로 해당 Process에 문제가 있어서 다시 시작하고자 할 때에는 SIGHUP, SIGTERM, SIGKILL의 순서로 시도해본다.
+ kill 명령어는 내부적으로 kill()이란 시스템 콜을 사용하여 구현하고, 프로세스 식별자(PID)로 지시한 프로세스와 프로세스 그룹 식별자(PGID)로 지시한 프로세스 그룹에 시그널을 보낸다.

+ **시그널**
  + 특정 이벤트가 발생했을 때 프로세스에게 전달하는 신호(메시지)이다.
  + 리눅스에서 프로세스끼리 통신할 때 사용한다.
  + 시그널 이벤트로는 HW 예외(나누기 0), SW 상태, 사용자 입력, 시스템 콜(kill) 등이 있다.
-------------------------------------------------------
*조사 자료 출처*
https://zzsza.github.io/development/2018/07/18/linux-top/
https://coding-factory.tistory.com/620
https://jhnyang.tistory.com/268
https://itwiki.kr/w/%EB%A6%AC%EB%88%85%EC%8A%A4_jobs
https://velog.io/@ogu1208/Linux-kill-%EB%AA%85%EB%A0%B9%EC%96%B4
https://yeoncoding.tistory.com/167
