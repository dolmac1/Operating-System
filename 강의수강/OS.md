# 인프런 강의 수강

## Chapter 1-2. 운영체제가 뭐길래?
- 정보량 I(x) = -log2P(x) (I(x) : 정보량, P(x) : 일어날 확률)
- 정보의 저장은 플립플롭, 정보의 전송은 데이터 버스
- 덧셈은 반가산기, 전가산기 뺄셈은 2의 보수 표현, 곱셈과 나눗셈은 덧셈과 뺄셈의 반복
- 실수 연산은 부동 소수점 표현법
- 함수는 GOTO 사용
- 프로그램 : 명령어의 집합
- 운영체제도 일종의 프로그램임
  - 항상 실행 중인 프로그램
  - 시스템 서비스를 어플리케이션에 제공하는 프로그램
  - 프로세스, 자원, 유저 인터페이스 등을 관리하는 프로그램


## Charpter 1-2. Introduction & O/S structures.
- 운영체제는 컴퓨터 유저(프로그램)와 하드웨어의 중간다리 역할
- 운영체제의 정의
  - universial 한 정의는 없음
  - 일반적인 정의로는 항상 동작하고 있는 프로그램(ex. kernel)
- 전통적인 컴퓨터 시스템
  - cpu, disk controller, usb controller, graphics adapter가 버스를 통해 메모리와 통신
- 컴퓨터를 실행하면 가장 처음에 실행하는 프로그램 : bootstrap (운영체제를 메모리에 로딩해주는 역할)
- 인터럽트
  - 하드웨어가 언제라도 인터럽트를 trigger시킬 수 있음
  - 트리거 시키면 cpu에 신호를 보내줌
- 폰노이만 아키텍처
  - fetch 하고 , excute 하는 형태의 구조
- 속도 : registers > chche > main memory(RAM) > SSD > hard disk > optical disk > magnetic tapes
- 용량은 반대 순서
- 동영상을 유튜브에서 보여줄 때 인터넷에서 받아오는 건 network device가, 실행은 lcd 화면이 하기때문에 cpu는 할일이없어서 Direct Memory Access(DMA) 방식을 통해서 보여줌
- Symmetric multiprocessing : 한개의 메모리에 여러개의 cpu가 접근
- Multi-core design : 듀얼코어, 쿼드코어 등등 같은 프로세스 칩 하나에 여러개의 코어가 붙어있는것
- Multiprogramming : 여러개의 프로그램을 동시에 실행시키는 것을 멀티 프로그래밍이라고 한다. cpu 가용률을 높여줄 수 있음
- Multitasking(=multiprocessing) : 멀티프로그램의 논리적 확장 개념
  - cpu는 매우 빠르기 때문에 하나의 일만 처리하면 노는 시간이 많아질 수 있음
  - 시간을 쪼개서(시분할) 여러개의 작업을 동시에 처리
  - cpu 스케쥴링이 필요함(어떤 프로세스를 다음에 실행할 것인가)
- 운영체제는 2개의 모드가 존재함(user mode, kernel mode)
  - 유저의 프로세스가 실행하다가 시스템 콜을 하면 user mode 에서 kernel mode로 바껴서 시스템콜을 처리하고 user mode로 돌아감
  - kernel mode에서만 하드웨어를 제어할 수 있음
  - 일반 프로세스가 하드웨어를 제어해서 불순한 동작을 할 수 없음
- 가상화 (Virtualization)
  - 가상화는 하나의 컴퓨터에 여러개의 운영체제를 수행해주는 것
  - vitual machine을 관리하기 위해서 virtual machine manager가 존재함
  - 하드웨어 위에 VMM을 올리고 VM을 올려서 각각의 프로세스를 실행해주는 형태
- 컴퓨팅 환경의 종류
  - Traditional Computing, Mobile Computing, Client-Server Computing, Peer-to-Peer Computing, Cloud Computing, Real-Time Embedded Systems
  - P2P 컴퓨팅의 발전이 비트코인이라고 할 수 있음
- OS가 제공하는 일
  - User interface
  - Program execution
  - I/O operation
  - File-system manipulation
  - Communication
  - Error Detection
  - Resource allocation
  - Logging
  - Protection and Security
- 시스템 콜
  - os 가 제공해주는 서비스를 시스템콜을 통해 접근
  - OS가 제공하는 API를 시스템 콜이라고 보면 됨
  - 항상 시스템 콜을 작성하면 힘드니까 라이브러리를 통해서 제공해줌


## 1-2 퀴즈
- 1번 : 정보량 = -log2확률 = -log2(1/4) = 2
- 2번 : not, and, or 게이트로 모든 연산 가능 = 1, nand 게이트 하나면 모든 연산 구현 가능 = 5 
- 3번 : 튜링 머신은 정지 문제 풀기 불가능 = 3
- 4번 : 컴퓨터의 명령어의 집합을 프로그램이라고 한다 = 4
- 5번 : 운영체제의 코어는 커널 = 1
- 6번 : 컴퓨터에 운영체제를 로드해주는 프로그램은 부트스트랩 = 3
- 7번 : 하나의 하드웨어에 여러개의 운영체제를 띄우는 것은 가상화 = 1
- 8번 : 운영체제에서 사용할 수 있는 서비스에 대한 인터페이스를 제공해주는 것은 시스템 콜 = 1