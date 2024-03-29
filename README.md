# Chapter1, 면접 스터디 전에 익혀보는 CS 지식

## 🎯 목표
- 1월까지 CS를 열심히 공부한다.
- 2월 동안 모의 면접 스터디를 진행한다.

## 🙋 진행방식
- **매주 목요일 오전 10시**에 게더타운에서 진행한다.
- 각자 준비해온 내용을 **깃허브에 공유**한다.
- 스터디 당일에 **랜덤한 1명이 발표**하고 서로 질문한다.

## 😋 커리큘럼
<details>
  <summary>OS</summary>

### Process & Thread
#### 💡 운영체제란 무엇인가? 
#### 💡 프로세스와 스레드에 대해 설명해주세요.
#### 💡 멀티 스레드의 장점 및 단점은 무엇인가?
#### 💡 멀티 프로세스 대신 멀티 스레드를 사용하는 이유
#### 💡 스레드에 스택을 독립적으로 할당하는 이유?
#### 💡 PC레지스터를 스레드마다 독립적으로 할당하는 이유?
#### 💡 자바 스레드란?
#### 💡 Thread-safe가 뭐에요?
#### 💡 세마포어와 뮤텍스를 설명해주세요.

### Scheduling
#### 💡 스케줄러란?
#### 💡 스케줄링 단계를 설명해주세요. 
#### 💡 스케줄링이 무엇인지와 목적을 설명해주세요
#### 💡 Context Switching이 뭐에요?
#### 💡 PCB에 저장되는 정보는 어떤 것들이 있나요?
#### 💡 비선점방식과 선점방식을 설명해주세요.
#### 💡 Round Robin 스케줄링이 뭐에요?
#### 💡 스케줄링 기법 중 FCFS의 단점과 해결 방법을 설명해주세요.

### 메모리 관리 전략
#### 💡 교착상태 vs 기아상태
#### 💡 운영 체제에서 에이징(Aging)는 무엇입니까?
#### 💡 외부 단편화와 내부 단편화란?
#### 💡 페이징의 장점과 단점은?
#### 💡 메모리 단편화 해결 기법에 대해 설명하시오.
#### 💡 페이지 교체 알고리즘 중 3가지를 선택해서 설명해주세요. 

### 가상 메모리
#### 💡 가상메모리의 역할은 무엇인가요?
#### 💡 Page Fault에 대해 설명하시오.
#### 💡 Demand Paging(요구 페이징)에 대해 설명하시오.
#### 💡 Swapping이 무엇인가요?
#### 💡 페이지 적중율을 극대화 시키기 위한 방법에는 무엇이 있는지 간략히 설명해주세요. 
#### 💡 Cache 메모리를 사용하는 이유에 대해 설명하시오.

### 커널
#### 💡 Kernel(커널)이란?
#### 💡 인터럽트가 필요한 이유 및 언제 발생되는지 말해주세요.
#### 💡 인터럽트 종류는 무엇이 있으며 우선순위를 말해주세요.
#### 💡 인터럽트 동작 과정을 말해주세요.
#### 💡 시스템콜이란 무엇이며 시스템 콜을 사용하는 예시를 말해주세요.
#### 💡 커널 모드와 유저 모드를 구분해 놓은 이유
#### 💡 커널 수준 스레드와 사용자 수준 스레드의 각각 장단점?

### 심화질문
#### 💡 부팅이란
#### 💡 파일 시스템이란
#### 💡 CISC(Complex)와 RISC(Reduced)의 차이
#### 💡 RISC가 단순하고 빠른 구조인데 왜 CISC를 사용하나요?
#### 💡 캐시와 레지스터의 차이점은 무엇인가요?
  
</details>

<details>
  <summary>Network</summary>

## [OSI 7 layers와 TCP/IP 4 layer](#osi-7-layers와-tcpip-4-layers-답변)
#### 💡 프로토콜이란?
#### 💡 패킷이란?
#### 💡 OSI 7 Layer와 각 계층에 대한 설명을 해주세요.
#### 💡 TCP/IP Layer와 각 계층에 대한 설명을 해주세요.
#### 💡 OSI 7 Layer 또는 TCP/IP Layer에서 계층화하는 이유가 무엇인가요?
#### 💡 Encapsulation과 Decapsulation을 서로 비교하며 설명해주세요
#### 💡 IP란? 
#### 💡 IP 주소란?
#### 💡 IPV4 vs IPV6 을 설명해주세요.
#### 💡 IPv4의 주소 부족현상을 해결하기 위해 현재 어떤 방법을 사용하고 있나요?

## [TCP와 UDP](#tcp와-udp-답변)
#### 💡 TCP와 UDP의 특징과 차이점을 설명해주세요.
#### 💡 TCP를 사용하는 대표적인 프로토콜은 무엇인가요?
#### 💡 3-Handshaking과 4-Handshaking의 과정을 설명해주세요. 
#### 💡 3-way handshaking 과정에서 클라이언트가 서버가 보낸 ACK+SYN을 받지 못하면?
#### 💡 클라이언트와 서버는 무엇인가요?
#### 💡 4-way handshaking 과정에서 클라이언트가 마지막에 ACK를 굳이 보내는 이유?
#### 💡 만약 Server에서 FIN 세그먼트를 전송하기 전에 전송한 패킷이 Routing 지연이나 패킷 유실로 인한 재전송 등으로 인해 FIN 패킷보다 늦게 도착하는 상황이 발생하면 어떻게 될까?
#### 💡 TCP의 연결 설정 과정(3단계)과 연결 종료 과정(4단계)이 단계가 차이나는 이유?
#### 💡 초기 Sequence Number인 ISN을 0부터 시작하지 않고 난수를 생성해서 설정하는 이유?
#### 💡 UDP에서 신뢰도를 보장하는 방법을 설명해주세요.

## [HTTP와 HTTPS](#http와-https-답변)
#### 💡 HTTP와 HTTPS를 설명해주세요
#### 💡 HTTP의 단점을 설명해주세요
#### 💡 HTTP1.1와 HTTP2.0 차이점은 무엇인가요?
#### 💡 HTTP는 왜 비연결성인가?
#### 💡 모든 웹 페이지에서 HTTPS 를 사용하지 않는 이유를 설명해주세요.
#### 💡 비대칭키 또는 공개키 암호화 방식은 무엇인가요?
#### 💡 HTTP REQUEST 방식 중 GET과 POST의 차이을 설명해주세요.
#### 💡 GET, POST를 제외하고 다른 방식들을 설명해주세요.
#### 💡 조회하기 위한 용도 POST가 아닌 GET 방식을 사용하는 이유?  
#### 💡 현대 웹 에서는 비연결성을 해결방법을 설명해주세요.  

## [DNS와 DHCP](#dns와-dhcp-답변)
#### 💡 도메인과 DNS가 무엇인지 설명해주세요  
#### 💡 Domain Name 구조를 설명해주세요.  
#### 💡 DNS round robin 방식의 문제점과 해결방법을 설명해주세요.  
#### 💡 DHCP 서버의 역할을 간단히 설명해주세요.  
#### 💡 Domain Name System 동작과정을 설명해주세요.  

## [로드밸런서](#로드밸런서-답변)
#### 💡 로드 밸런싱을 설명해주세요.  
#### 💡 L4 로드 밸런싱과 L7 로드 밸런싱에 대해 설명하고, 차이를 말해보세요  
#### 💡 게이트웨이란?  
#### 💡 서버에 트래픽이 주어졌을 때 어떻게 응답속도를 개선할 수 있는가?  

## 01-2. Web of Network Overview
## [WEB](#web-답변)
#### 💡 클라이언트와 서버는 무엇인가요?  
#### 💡 url과 uri에 대해 각각 설명해주세요  
#### 💡 브라우저에 "www.google.com" 입력하면 어떤일이 일어날까요?  
#### 💡 RESTful API란 무엇인가요?  
#### 💡 Ajax는 무엇인가요?  
#### 💡 Ajax의 장점과 단점은 무엇인가요?  
#### 💡 CORS는 무엇인가요?  
#### 💡 CORS preflight는 무엇인가요?  
#### 💡 소켓이란 무엇인가요?  
#### 💡 DOM과 가상DOM  
#### 💡 OAuth란 무엇인가요?  
#### 💡 SPA   

## [cookie와 session](#cookie와-session-답변)
#### 💡 cookie와 session에 대해 설명해주세요  
#### 💡 Session 동작 순서를 설명해주세요.  
#### 💡 cookie를 쓰는 이유를 설명해주세요  
#### 💡 세션 인증방식 단점  
#### 💡 토큰 인증방식
#### 💡 JWT   
#### 💡 토큰 인증방식 단점  
#### 💡 쿠키 인증방식 해결방안  

</details>

## 🏃 발자취
- 23.12.21 : `Process & Thread`
- 23.12.28 : `Scheduling`
- 24.01.04 : `메모리 관리 전략`
- 24.01.11 : `가상 메모리`
- 24.01.18 : `커널`
- 24.01.25 : `심화질문 & 복습`
- 24.02.06 : `OSI 7 layers와 TCP/IP 4 layer`
- 24.02.08 : `TCP와 UDP`
- 24.02.15 : `HTTP와 HTTPS`
- 24.02.23 : `DNS와 DHCP & 로드밸런서`
- 24.02.29 : `WEB & Cookie와 Session`

## 📚 Reference
1. [SSAFY 친구들](https://github.com/SSAFY-CS-STUDY/Tech_interview)
2. [외국 인터뷰 자료](https://github.com/arialdomartini/Back-End-Developer-Interview-Questions)
3. [백엔드 인터뷰 자료](https://github.com/ksundong/backend-interview-question)
4. [설로인 면접 질문](https://github.com/sirloin-dev/meatplatform/blob/master/job-description/interview-questions.adoc)
