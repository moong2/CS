**Round-Robin**
선점형 [[FCFS]]와 유사
### 원리
**time quantum** : 10 ~ 100ms의 작은 시간 단위
1️⃣  FIFO queue와 동일하게 프로세스가 ready queue에 등록
2️⃣ 새로운 프로세스는 queue의 tail에 등록
3️⃣ 프로세스를 실행할 때 head에 위치한 프로세스를 선점하고, 1번의 time quantum 부여
4️⃣ 타임 퀀텀이 만료될 경우 타이머 [[인터럽트]]가 발생해 큐의 맨 뒤로 이동, 프로세스 작업이 완료되면 제거

![](https://i.imgur.com/7otPP6y.png)
1 time quantum = 4ms
![](https://i.imgur.com/ZahuN9I.png)
P1 대기 시간 : 6 (10 - 4)
P2 대기 시간 : 4
P3 대기 시간 : 7
>💡 총 대기 시간 : (6 + 4 + 7) / 3 = 5.66
### 장점
각 프로세스에게 균등한 처리량 보장
### 단점
성능, Turnaround Time이 Time quantum에 달려 있음
	![](https://i.imgur.com/FSRPVe2.png)
- 매우 클 경우, FCFS와 다를 바가 없음
- 매우 작을 경우, 과도한 인터럽트가 일어남
> 💡 CPU burst의 80%가 time quantum보다 짧은 것이 최적