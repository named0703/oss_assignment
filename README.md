# 220605 oss_assignment
 오픈소스SW개론 두 번째 과제입니다.  


### 목차  
1. [리눅스 명령어](#리눅스-명령어-top,-ps,-jobs,-kill)  
1.1 [top](#1.-top)  
1.2 [ps](#2.-ps)  
1.3 [jobs](#3.-jobs)  
1.4 [kill](#4.-kill)  
2. [vim 에디터 매크로 활용방법](#vim-에디터-매크로-활용방법)  



## 리눅스 명령어 top, ps, jobs, kill
### 1. top
Linux 명령어 top은 실시간으로 실행 중인 프로세스를 보여주며 커널 관리 작업을 표시한다. 또한 CPU 및 메모리 사용량을 포함한 정보도 함께 표시한다.  

아래의 사진은 top을 입력한 결과 사진이다.  
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
5. VIRT : 프로세스가 소비하고 있는 총 메모리  
6. RES : RAM에서 사용중인 메모리의 크기  
7. SHR : 공유메모리  
8. S : 프로세스 현재 상태  
9. %CPU : CPU 사용량
10. %MEM : 메모리 사용량  
11. TIME+ : 가동시간  
12. COMMAND : 해당 프로세스를 실행한 커맨드  

* ### top 명령어 옵션
|옵션|설명|
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

### 3. jobs

### 4. kill


## vim 에디터 매크로 활용방법
