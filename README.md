# 220605 oss_assignment
 오픈소스SW개론 두 번째 과제입니다.  


### 목차  
1. [리눅스 명령어](#리눅스-명령어-top,-ps,-jobs,-kill)  
1.1. [top](#1-top)  
1.2. [ps](#2-ps)  
1.3. [jobs](#3-jobs)  
1.4. [kill](#4-kill)  
2. [vim 에디터 매크로 활용방법](#vim-에디터-매크로-활용방법)  



## 리눅스 명령어 top, ps, jobs, kill
### 1. top
Linux 명령어 `top`은 실시간으로 실행 중인 프로세스를 보여주며 커널 관리 작업을 표시한다. 또한 CPU 및 메모리 사용량을 포함한 정보도 함께 표시한다.  

아래의 사진은 top 명령어를 입력한 결과 사진이다.  
![top_image](./image/top_.PNG)  
**Line 1** : System time, Uptime, User 및 load 평균  
**Line 2** : Tasks 정보, process 상태    
**Line 3** : CPU 사용량, 모든 값의 총 합은 100%  
(us : 유저 영역의 CPU 사용률, sy : 커널 영역의 CPU 사용률, ni : 우선순위 설정에 사용하는 CPU 사용률, id : 사용하고 안하는 비율, wa : IO가 완료될때까지 기다리고 있는 CPU 비율, hi : 하드웨어 interrupt에 사용되는 CPU 사용률, si : 소프트웨어 interrupt에 사용되는 CPU 사용률, st : CPU를 VM에서 사용하여 대기하는 CPU 비율)  
**Line 4~5** : Memory 사용량(Line 4 (Mem) : RAM 메모리 공간, Line 5 (Swap) : Swap 메모리 공간  
**Line 6**  
1. PID : 프로세스 ID  
2. USER : 실행한 USER 이름
3. PR : 스케줄링되는 우선순위  
4. NI : nice 값  
5. VIRT : 가상메모리 사용량  
6. RES : resident 메모리   
7. SHR : 공유메모리  
8. S : 프로세스 현재 상태  
9. %CPU : CPU 사용량
10. %MEM : 메모리 사용량  
11. TIME+ : 가동시간  
12. COMMAND : 해당 프로세스를 실행한 커맨드  

* ### top 명령어 옵션
|옵션|내용|
|---|-----|
|-a|메모리 사용에 따라 정렬|
|-b|Batch mode, 배치 모드에서 시작|
|-c|Toggle command line/program name, 명령어 라인을 보여준다|
|-d [N]|Delay time interval, 화면 갱신 시간 설정|
|-h|Help, 도움말|
|-H|Threads mode operation, 모든 개별 threads 출력|
|-i|Idle process toggle, 좀비(zombie)또는 Idle 상태 무시|
|-n|Limit iteration number, 실행 주기 설정|
|-p [PID]|특정 프로세스만 출력|
|-s|Secure mode operation, 보안 모드|
|-S|Cumulative time toggle, 누적 시간 토글이 On일 경우 각 프로세스가 CPU를 사용한 시간과 함께 출력|
|-u [ID or name]|지정된 유효 사용자에 의한 프로세스만 출력|
|-U [ID or name]|지정된 사용자에 의한 프로세스만 출력|
|-v|version, 라이브러리 버전 출력|

* ### top 실행 중 명령어
|키|설명|
|---|-----|
|space bar|Refresh|
|k|kill, process 종료|
|r|nice, 우선순위 값 변경|
|c|명령 인자 on/off|
|l|첫번째 행 on/off|
|t|Task 항목 on/off|
|m|CPU 상황 on/off|
|n|출력할 프로세스 개수 설정|
|u|입력한 유저의 프로세스만 출력|
|i|좀비(zombie)또는 Idle 상태 무시|
|d|Refresh 간격 조절|
|Z|출력 색상 변경|
|q|top 종료|

**정렬**
|키|정렬 기준 column|설명|
|---|-----|-----|
|M|%MEM|memory usage로 정렬|
|P|%CPU|CPU usage로 정렬|
|N|PID|process ID로 정렬|
|T|TIME+|running time로 정렬|
|R||오름차순 내림차순 변경|



### 2. ps
Linux 명령어 `ps`는 현재 실행중인 프로세스 목록을 보여주는 명령어이다.  

아래의 사진은 ps 명어를 입력한 결과 사진이다.  
![ps_image](./image/ps.PNG)  
**정보**
1. PID : 프로세스 ID    
2. TTY : 터미널  
3. TIME : CPU 점유 시간    
4. CMD : 프로세스가 수행한 명령어  

ps 명령어는 `ps -efl` 처럼 주로 **옵션과 함께 사용**된다.


ps의 옵션은 세가지 유형으로 나눠진다.  
1. UNIX : 단일 대시(-)가 앞에 온다.
2. BSD : 대시 없이 사용된다.
3. GNU : 두 개의 대시(--)가 앞에 온다.  

|옵션|내용|
|---|-----|
|-A|모든 프로세스 출력|
|a (BSD)|터미널과 연관된 프로세스 출력|
|-a|세션 리더와 터미널과 연관된 프로세스를 제외한 프로세스 출력|
|-d|세션 리더를 제외한 모든 프로세스 출력|
|-e|실행중인 모든 프로세스 출력|
|-f|full format으로 출력, ppid 확인 가능|
|-l|long format으로 출력|
|-o|출력 column 지정|
|-p|특정 PID의 프로세스 출력|
|u (BSD)|사용자 정보 출력, 사용자 지향 형식|
|-u|특정 사용자의 프로세스 정보 출력|
|x (BSD)|터미널에 종속되지 않는 프로세스 출력|
|-x|로그인 상태에 있는 동안 아직 완료되지 않은 프로세서 출력|
|--help|도움말|


`ps -ef | grep root`  
위와 같이 파이프(|)를 통해 다른 명령어와 함께 사용 가능하며 grep으로 필터링이 가능하다.  
BSD 계열에서는 `ps aux`를 많이 사용한다. `ps aux`는 시스템에 동작중인 모든 프로세스를 소유자 정보와 함께 출력한다.


### 3. jobs

### 4. kill


## vim 에디터 매크로 활용방법
