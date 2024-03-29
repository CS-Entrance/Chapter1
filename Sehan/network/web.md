

# 

**💡 클라이언트와 서버는 무엇인가요?**

<aside>
💡 클라이언트는 다른 호스트의 데이터나 리소스를 요청하는 호스트입니다,
서버는 요청에 따라 다른 호스트에게 리소스나 데이터를 제공합니다.

</aside>

**💡 url과 uri에 대해 각각 설명해주세요**

<aside>
💡 URL(Uniform Resource Locater)은 자원의 위치를 나타내는 것이고 URI(Uniform Resource Indicator)는 자원의 식별자를 나타냅니다.
URI는 URL을 포함하는 관계입니다.

</aside>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cafb301d-6dbe-47c4-b31e-d27546450740/af8e4486-5bd7-4429-9b11-1cc0088a2d5e/Untitled.png)

**💡 브라우저에 "[www.google.com](http://www.google.com/)" 입력하면 어떤일이 일어날까요?**

<aside>
💡

1.  사용자가 브라우저에 주소를 입력한다.
2. 브라우저는 DNS 서버에 요청하기 전에 캐시를 확인하여 정보를 찾는다.
3. 만약 정보를 찾기 못하였다면 DNS 리커서가 root 서버에 반복적 질의를 보낸다.
4. SLD 네임 서버로부터 최종적으로 IP 주소를 응답받는다.
    1. 해당 도메인에 해당하는 정보는 일정 시간 캐싱된다.
5. 브라우저는 응답 받은 IP 정보로 요청을 전송하고 HTTP 연결을 시도한다.
6. 연결이 성립되면 해당 url의 html 정보를 요청한다.
    1. WAS : 동적인 웹 페이지에 대해 응답 (웹 어플리케이션)
    2. 웹서버 : 정적인 어플레케이션에 대해 응답
7. 응답을 받은 브라우저는 브라우저에 페이지를 띄울 수 있다.
    1. 만약 4xx 5xx 응답을 받는다면 에러 페이지가 나온다.
    2. 3xx는 리다이렉트 , 1xx는 단순 정보
</aside>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cafb301d-6dbe-47c4-b31e-d27546450740/d0b86f64-f8af-4864-a632-e41328449e00/Untitled.png)

**💡 RESTful API란 무엇인가요?**

<aside>
💡 Representational State Transfer (이하 REST) 란 자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 것입니다.

REST는 HTTP 프로토콜을 그대로 사용하기 때문에 웹의 장점을 극대화 할 수 있습니다.

이러한 특징 덕분에 RESTful한 아키텍쳐를 사용해서 대규모의 고성능 통신을 안정적으로 지원할 수 있으며, 이것을 쉽게 구현하고 여러 플랫폼에서 사용할 수 있습니다.

API(**Application Programming Interface**)란 다른 애플리케이션과 통신할 수 있도록하는 것을 의미합니다.

클라이언트와 리소스 사이의 게이트웨이 역할을 수행합니다.

결국 REST API는 REST 아키텍쳐 기반으로 API를 구현한 것입니다.

</aside>

**💡 Ajax는 무엇인가요?**

<aside>
💡 자바스크립트를 이용해서 서버와 브라우저가 비동기 방식으로 데이터를 교환할 수 있게 해주는 것입니다.
빠르게 동작하는 동적인 웹을 만들기 위해 Ajax를 이용하여서 웹 페이지 전체를 다시 로딩하지 않고도, 웹 페이지의 일부분만을 갱신할 수 있습니다.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cafb301d-6dbe-47c4-b31e-d27546450740/0011ad21-97a1-4a10-8f04-7260f4b43b11/Untitled.png)

</aside>

**💡 Ajax의 장점과 단점은 무엇인가요?**

<aside>
💡 홈페이지의 일부만 먼저 띄울 수 있으므로 빠르게 동작하는 동적인 웹을 구성하기 용이합니다.
웹 페이지가 로드된 후에도 데이터 요청을 보낼 수 있습니다.

단점으로는 클라이언트 풀링 방식을 사용하여서 서버 푸시 방식의 실시간 서비스 구성이 어렵습니다.
또한 히스토리 관리가 안되어서 보안에 좀 더 신경써야합니다.

</aside>

**💡 CORS는 무엇인가요?**

<aside>
💡 동일 출처 정책인 SOP의 반대 개념으로 두 출처(프로토콜 , 도메인 , 포트)가 서로 다르더라도 리소스 요청과 응답을 풀어주는 설정입니다. 즉 교차 출처 리소스 공유 정책이다.
CORS를 허용해줌으로써 도메인, 포트, 프로토콜이 다르더라도 리소스를 요청하고 응답받을 수 있다.

</aside>

**💡 CORS preflight는 무엇인가요?**

<aside>
💡 브라우저에서 cross-origin 요청을 보내기 전에 서버에서 어떤 origin 과 메소드들을 허용해주고 있는 지 미리 요청을 보내고 알아보는 것이다.

</aside>

**💡 소켓이란 무엇인가요?**

<aside>
💡 소켓이란 프로그램에서 네크워크 상에서 데이터를 주고 받을 수 있게 해주는 연결부이자 데이터의 종착점입니다. 
소켓을 통해 데이터를 주고 받으려면 양측 다 소켓이 생성되어있어야합니다.

</aside>

**💡 DOM과 가상DOM**

<aside>
💡

</aside>

**💡 OAuth란 무엇인가요?**

<aside>
💡

</aside>

**💡 SPA**
