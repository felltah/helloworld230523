# helloworld230523
# 20233116 박진우 *과제2*

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
![리눅스 top -b -n 1](https://github.com/felltah/helloworld230523/assets/126939612/49a1eac1-f768-4d19-8382-83de398838fc)
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
+**ps**
  + 현재 실핸중인 프로세스 목록과 상태 보여줌.
  + 
  

https://zzsza.github.io/development/2018/07/18/linux-top/

https://coding-factory.tistory.com/620

https://jhnyang.tistory.com/268

