### 💡 교착상태 vs 기아상태

**교착상태 (Deadlock)**

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/0d42808d-cb1f-420d-b9b3-f002787287ac)

위 그림처럼 2개 이상의 프로세스가 자원을 할당받은 상태에서 상대방의 작업이 끝나기를 “무한 대기”해서 다음 단계로 진행되지 못하는 상태를 “`교착상태(DeadLock)`”이라 한다.

✨ 교착상태 발생 가능성은 아래 4가지 조건을 “**모두**” 충족해야 발생할 가능성이 있다.

1. **상호배제 (Mutual Exclustion)** - 자원은 한 번에 한 개의 프로세스만 사용할 수 있다. 
2. **점유대기 (Hold and Wait)** - 자원을 최소한 하나 보유하면서 다른 프로세스에 할당된 자원을 얻기위해 기다리는 프로세스가 존재한다
3. **비선점 (No preemption)** - 자원은 선점할 수 없다 (다른 프로세스의 자원의 사용이 끝날 때 까지 자원을 사용할 수 없다)
4. **순환대기 (Circular wait)** - 다른 프로세스가 보유한 자원을 얻기위해 대기하는 것

✨ 교착상태를 “`해결`”하기 위한 방안으로는 크게 4가지가 있다

**1️⃣ 예방**

위 교착상태 발생 조건 4가지를 제거해준다

- 상호배제 제거
- 점유대기 제거
- 비선점 제거
- 순환대기 제거

단, 예방을 위한 방법은 자원의 낭비가 발생하여 성능에 문제가 발생할 수 있다

**2️⃣ 회피**

교착 상태가 발생한다면 교착 상태를 피해가는 해결 방안이다

- 자원 할당 알고리즘
- 은행원 알고리즘(자원 할당 거부)
    - 자원을 할당한다면 문제가 발생하는지 확인 후 할당하는 방식
    - 하지만, 할당할 수 있는 자원의 수와 사용자 수가 일정해야 하며

**3️⃣ 무시**

1번인 예방과 2번인 회피를 사용한다면 성능에 큰 문제가 발생할 수 있다.

따라서 교착 상태의 정도를 판단 후 상태를 해결하지 않고 무시하고 자원을 사용하는 방법이다.

- 자원 할당 그래프나 알고리즘을 통해 교착 상태를 탐지한다

**4️⃣ 회복**

교착 상태가 발생했을 경우 해결하는 방법이다. 

교착 상태를 일으킨 프로세스를 종료하거나 할당된 자원을 해제시킨다.

지속적인 모니터링이 필요한 방법이다.

**기아상태 (Starvation**

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/77bfcb89-ea1c-4339-9f60-b603a5807b81)

위 그림처럼 우선순위가 낮은 프로세스는 계속해서 실행되지 못하는(자원을 할당받지 못하는) 상황을 “`기아상태(Starvation)`” 이라 한다.

기아상태를 해결하기 위한 방안으로 대표적인 에이징(Aging) 기법이 있다.

**정리**

| DeadLock | Starvation |
| --- | --- |
| 여러 프로세스가 동일 자원 점유를 요청할 때 발생 | 여러 프로세스가 부족한 자원을 점유하기 위해 경쟁할 때 발생 |

### 💡 운영 체제에서 에이징(Aging)는 무엇입니까?

에이징의 원래 뜻은 “노화”이다. 

즉, 시간(대기시간)이 지날수록 나이(우선순위)가 먹도록 하는 것!

이렇게 하면 오래 기다린 프로세스는 CPU 자원을 할당받을 수 있게 된다.

에이징은 위에서 설명한 기아상태 (starvation)의 해결방법이다.

보통 우선순위 기반의 스케줄링에서 사용된다.

`에이징` 외에도 기아 현상을 해결하기 위한 방법으론 `피드백`(FeedBack), `페어 스케줄링`(Fair Scheduling)이 있다.

> **피드백(FeedBack)**
프로세스가 CPU를 사용할수록 우선순위를 감소시키는 방식
자주 CPU를 이용하는 프로세스는 낮은 우선순위로 밀려나면서 동시에 오랫동안 기다린 프로세스는 우선순위가 높아지게 된다
보통 피드백은 다단계 큐나 다단계 피드백 큐와 같은 스케줄링에서 사용된다
> 

> **페어 스케줄링(Fair Scheduling)**
모든 프로세스에게 동일한 비율의 CPU 시간을 할당해주는 방식
예를 들어, 10개의 프로세스가 있다면 각각 10%의 CPU 시간을 할당받게 된다.
이렇게 되면 어떤 프로세스도 기아 상태에 빠지지 않게 된다. 
보통 페어 스케줄링은 리눅스와 같은 OS에서 사용되는 스케줄링 알고리즘이다
> 

### **💡 외부 단편화와 내부 단편화란?**

**✨ 외부 단편화 (External Fragmenation)**

- 남아있는 메모리의 크기가 실행하고자 하는 프로세스보단 크다
- 하지만, 남아있는 메모리는 **연속적이지 않은 공간에 존재**하여 프로세스를 실행시키지 못하는 현상

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/4c812b6a-8f29-4114-9af9-74eb30995308)

위 그림과 같이 Process C는 실행시키기 위해 80MB의 메모리 공간이 필요하다

남은 메모리 공간은 50MB + 50MB으로 100MB가 남아있지만 연속적이지 않아 80MB의 공간이 필요한 Process C를 실행시킬 수 없다

이런 현상을 `외부 단편화`라고 한다.

**✨ 내부 단편화 (Internal Fragmenation)**

- Partitioning 상황에서 발생하는 문제
- Partition의 크기가 프로세스의 크기보다 커서 메모리가 남지만, 남은 공간은 다른 프로세스가 사용할 수 없어 낭비되는 현상
- 필요한 양보다 더 큰 메모리 공간에 할당되어 낭비가 되는 현상

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/8626f0e3-783b-433f-a395-74786c81e858)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/f3a6b41d-956d-453c-9635-724b743f67a2)

즉, 80MB만큼만 필요한데 100MB에 할당되어 20MB가 버려지게 되는 것

### 💡 페이징의 장점과 단점은?

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/93914247-94a0-4749-98aa-d7d6bae959ac)

프로세스를 나눈 조각 - page, 메모리를 나눈 조각 - frame

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/41945c44-f3c2-43fe-986e-9702364076d4)

페이징은 프로세스가 할당받은 메모리 공간을 동일한 페이지 단위로 나누어 연속되지 않은 서로 다른 위치에 저장하는 물리적 메모리 관리 기법이다

페이징 기법은 Partitioning, Buddy system와 다르게 물리적인 주소가 연속적이지 않은 상황에서도 매핑이 가능하도록 한다

주소 관리를 위해 모든 프로세스가 각각의 주소 변환을 위한 `Page Table`을 가진다

**장점**

- 외부 단편화 해결 → 물리적 메모리 공간을 효율적으로 사용할 수 있다
- 유연한 메모리 관리
    - 페이지 크기를 조절함으로써 다양한 크기의 프로세스를 다룰 수 있다
    - 할당과 해제가 프로세스 단위가 아닌 page 단위이므로 간단하다
- Swap out 간단 → Page Table을 통해 주소 변환을 간단하게 처리할 수 있다

**단점**

- 외부 단편화는 해결했지만 `내부 단편화`는 여전히 해결하지 못한다
    
  ![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/3e17758d-7a62-4224-953f-d242fb2528ba)
    
    - 프로세스 내에서 페이지 단위로 나누는 과정에서 빈 공간이 남을 수 있어 내부 단편화 문제의 발생 가능성이 존재한다
- `Page Table overhaed` - 큰 주소 공간의 경우 페이지 테이블 크기가 커져 메모리 오버헤드가 발생할 수 있다. 또한 page table은 프로세스마다 존재하며 메인 메모리에 존재한
- `메모리에 2번 접근해야 한다` - page table에 1번, 실제 주소를 구해 메모리에 1번. 총 2번 접근해야 한다.
    - 이러한 현상을 보완하기 위해 `TLB`(Translation Look-aside Buffer)라는 하드웨어의 도움을 받아 해결할 수 있다

> **TLB(Translation Look-aside Buffer)**
참조했던 페이지를 담아주는 “**캐시**” 역할이다
즉, 가상 메모리 주소를 물리적인 주소로 변환하는 속도를 높기위해 사용하는 **캐시**이다
Key-Value  쌍으로 데이터를 관리하는 acssociative memory이며 CPU는 page table보다 TLB를 우선 참조한다
> 

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/c98f5eb9-a1ec-48a0-abcc-b30d680f5e86)

### 💡 메모리 단편화 해결 기법에 대해 설명하시오.

✨ **외부 단편화 해결방법**

1️⃣ Compaction (압축) - 흩어져 있는 공간을 메모리 재배치를 통해 하나의 연속적인 공간으로 합치는 기법

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/2d1ddf5a-fbe5-4b34-a36b-3f86cc677d4b)

2️⃣ Paging (페이징) - 가상 메모리 사용 But 내부 단편화는 여전히 존재

페이지의 크기는 “**일정**”하므로 외부 단편화는 해결할 수 있으나 내부 단편화 문제가 발생할 수 있다

✨ **내부 단편화** **해결방법**

1️⃣ Segmentation (세그맨테이션) - 가상 메모리 사용 But 외부 단편화 존재

Segment(세그먼트)의 크기는 “**가변적**”이므로 내부 단편화는 해결할 수 있으나 외부 단편화 문제가 발생할 수 있다

우리가 식자재를 보관할 때 페이징은 모두 파, 버터를 모두 같은 단위로 잘라서 보관을 해야한다

하지만, 세그맨테이션은 파의 흰 부분은 크게, 잎 부분은 작게, 버터는 더 작은 단위로 잘라서 보관할 수 있는 방법이다

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/c211dd2f-aa96-4df0-865a-9c869dac2e3a)

segment의 크기가 가변적이므로 **시작 주소(`base`)**와 **크기(`limit`)**를 가지고 있다

단점은 서로 다른 크기의 segment들이 메모리에 적재되고 제거되는 일이 반복되다 보면 작은 조각의 자유 공간이 많아지면서 `외부 단편화` 문제가 발생할 수 있다.

마찬가지로 예를 들면, 페이징 기법으로 식자재를 냉장고에 보관할 때 냉장고 크기에 딱 맞게 저장할 수 있어 냉장고에 빈 자리가 생기지 않는다 (= 외부 단편화가 발생하지 않는다)

하지만, 세그멘테이션 기법으로 식자재를 냉장고에 보관할 때 크기를 가변적으로 두었기 때문에 식자재 단위는 자유롭게 가져올 수 있지만 냉장고에 빈 자리가 생길 수 있다 (= 외부 단편화가 발생할 수 있다)

**✨ 단편화 해결방법**

1️⃣ Memory Pool (메모리 풀)

미리 공간을 할당해놓고 반납하기 때문에 외부 단편화 발생X

또한, 필요한 크기만큼 할당을 하기 때문에 내부 단편화 발생X

고정된 크기의 블록을 할당해서 메모리 동적 할당을 가능하게 한다

memory pool이라고 불리는 동일한 사이즈의 메모리 블록들을 미리 할당해두고 프로세스들이 필요할 때마다 사용하고 반납하는 기법

단, 미리 할당해두기 때문에 “`메모리 누수`”가 발생할 수 있다

사용하지 않는 시점에도 메모리에 할당되어 있 때문이다.

⇒ 메모리의 할당, 해제가 빈번할 때 Memory Pool방식이 효율적이다.

PS. Paging VS Semgentation

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/e0d492e6-5385-45f4-a00a-8dcc5223d3df)

### 💡 페이지 교체 알고리즘 중 3가지를 선택해서 설명해주세요.

요구 페이징으로 필요한 페이지가 메모리에 없을 때 page-fault가 발생하고 Backing Store에서 해당 페이지를 찾아 빈 프레임에 로딩해야 하는데, 이때 빈 프레임이 없을 경우 희생 당할 프레임을 고르는 알고리즘 

→ 페이지 교체 알고리즘 

→ page-fault 발생 비율을 줄이는 것이 목표  

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/0609e76a-a2db-4a72-939e-d76eb4125e84)

1️⃣ FIFO (First in First Out)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/fe9c8f5a-a97c-4884-aa81-d455556c5c7f)

- 선입선출 페이지 교체 알고리즘
- 들어온 시간을 저장하거나 올라온 순서를 Queue로 구현
- 맨 위에 있는 페이지는 가장 오래된 페이지, 새로운 페이지는 맨 아래
- 맨 위에 있는 페이지가 자주 사용되는 페이지일 수도 있다 → **성능 저하**
- 구현이 간단하지만 성능이 좋지 않는 편이다
- ****************Belady`s Anomaly 현상이 발생할 수 있다****************
    - 프레임의 갯수가 많아져도 page-fault가 줄어들지 않고 늘어나는 현상을 말한다
    
    ![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/aac904ed-31e5-470e-aabc-5c222b429cdd)
    
    - FIFO 알고리즘은 프레임의 갯수가 많아져도 page-fault가 줄어들지 않는다

2️⃣ LRU (Least Recently Used)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/498feb37-507a-4a83-84c1-f853bf52ad61)

- **최근 최소 사용** 페이지 교체 알고리즘
- 즉, 가장 오랫동안 사용되지 않은 페이지를 스왑 영역으로 옮긴다
- FIFO 알고리즘보다 성능은 우수하지만 **페이지 사용 횟수**를 표시하는 데에 추가 공간이 필요하므로 메모리 낭비가 존재한다
- 그림에선 A가 가장 처음에 들어왔지만 1번밖에 사용되지 않아 A가 스왑되고 D가 4번째에 들어오게 된다

3️⃣ LFU (Least Frequently Used)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/1d1dff2b-f0dc-4b3c-b919-323363f9047e)

- 최소 빈도 사용 페이지 교체 알고리즘
- 즉, 페이지가 몇 번 참조되었는지를 기준으로 하며 가장 적게 참조된 페이지를 스왑 영역으로 옮긴다
- FIFO 알고리즘보다 성능은 우수하지만 **페이지 참조 횟수(빈도)**를 표시하는 데에 추가 공간이 필요하므로 메모리 낭비가 존재한다
- 그림에선 A,B,C 전부가 1번 사용됐지만 가장 먼저 들어온 것은 A이므로 A를 스왑하고 D가 4번째에 들어오게 된다
- 6번째에선 D가 가장 맨위에 있으면서 D,C 빈도 1으로 가장 적기때문에 D를 스왑하고 A가 들어오게 된다

4️⃣ MFU (Most Frequently Used)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/973285fe-c932-4399-86cd-536ed4152d74)

- LFU와 반대로 **참조 횟수가 가장 많은 페이지**를 교체하는 알고리즘

5️⃣ NUR (Not Used Recently)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/e6375633-a93c-46ca-b3fd-7d61d73e85a7)

- 추가 비트 2개만 사용하여 미래를 추정하는 알고리즘
    - 참조 비트 → PTE의 접근 비트를 가르킴 (접근하면 1)
    - 변경 비트 → PTE의 변경 비트를 가르킴 (변경되면 1)
- LRU, LFU 페이지 교체 알고리즘과 성능이 비슷하지만 불필요한 공간 낭비를 해결했다
- 가장 먼저 (0, 0)인 페이지를 선정하고 없다면 (0, 1) → (1, 0) → (1, 1) 순서로 선정된다
- 만약 모든 페이지가 (1, 1)이 되면 모든 페이지 비트를 (0, 0)으로 초기화한다

6️⃣ OPT (최적)

![image](https://github.com/CS-Entrance/Chapter1/assets/89267864/7c9a1739-9c9f-4a43-881e-e5243dccf428)

- 앞으로 사용하지 않을 페이지를 스왑 영역으로 옮긴다
- 미래의 메모리 접근 패턴을 보고 대상 페이지를 결정한다 → 성능 향상
- 하지만, 미래의 메모리 접근 패턴을 안다는 것은 사실상 “불가능” → 실제로 구현 X
- C가 9번째에서 가장 늦게 사용되므로 C를 스왑하고 D를 4번째에서 삽입했다

- FIFO(First In First Out)는 가장 간단한 페이지 교체 알고리즘으로 **먼저 물리 메모리에 들어온 페이지 순서대로 페이지 교체 시점에 먼저 나가게 되는** 알고리즘입니다.
- OPT(OPTimal replacement)는 가장 오랫동안 사용되지 않을 페이지를 찾아 교체하는 알고리즘입니다.
- LRU(Least Recently Used)는 페이지 교체 알고리즘 중 가장 많이 쓰이는 알고리즘으로 가장 오랫동안 사용되지 않은 페이지를 선택하여 교체하는 알고리즘입니다.
