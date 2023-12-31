1. HTTP란? 

하이퍼텍스트 전송 프로토콜은 하이퍼텍스트 링크를 사용하여 웹 페이지를 로드하는 데 사용된다. HTTP를 통한 일반적인 흐름에는 클라이언트 시스템에서 서버에 요청한 다음 서버에서 응답 메시지를 보내는 작업이 포함된다. 예를 들면 '클라이언트가 웹 페이지에서 링크가 걸려있는 텍스트를 클릭(요청)하면 링크를 타고 새로운 페이지로 넘어간다(응답)'. 따라서 우리가 사용하는 웹 브라우저에서 인터넷 주소 맨 앞에 들어가는 http://가 바로 이 프로토콜을 사용해서 정보를 교환하겠다는 표시인 것이다.


2. HTTP의 구조

HTTP 버전 유형 URL HTTP 메서드 HTTP 요청 헤더 선택 사항인 HTTP 본문.

HTTP는 요청(Request)와 응답(Response)로 구성되어 있고, 클라이언트가 요청을 하면 서버가 응답을 하는 구조로 되어 있다. HTTP는 FTP나 텔넷과는 다르게 비연결식이다. HTTP는 클라이언트가 서버에 정보를 요청하면 응답 코드와 내용을 전송하고 클라이언트와 연결을 종료한다. 우리가 웹 브라우저에 접속을 했다고 가정하자. 접속하면 클라이언트는 GET명령을 웹 서버에 전송한다. GET요청을 받은 브라우저는 응답 코드와 메시지를 전송하고, 그것을 브라우저가 화면에 뿌려주는 것이다.


3. HTTP와 TCP의 관계

HTTP통신은 소켓 연결 과정(3 way- Handshake)이 없으므로 간단한 정보들을 주고 받을 때 사용하면 좋습니다. 웹 페이지 처럼 단순한 데이터들로만 구성이 되어 있는 경우가 된다.
TCP통신 역시 위와 같은 예시로 사용할 수 있지만, 이는 서버에 소켓 연결로써 계속 언제든 통신을 주고 받을 준비를 하기 때문에 여러 Client가 붙으면 그만큼 서버에 부담이 된다. 하지만 실시간 통신이 필요하다면 사용할 수 있다.

HTTP웹에서 TCP통신은 가능. 우리는 이것을 웹소켓(websocket)이라고함

TCP통신은 Handshake라는 과정으로 서로가 통신을 할 수 있는 상태를 먼저 인증을 하고 나서 통신을 하는 연결지향적인 양방향 통신이다. 이는 서로에게 언제든 실시간으로 상태를 보낼 수 있으며, 받을 수도 있다. HTTP통신도 기본적으로 TCP 위에서 작동이 되는 구조이며, Handshake라는 과정을 거치며 소켓을 각자 생성하여 서로에 대한 상태를 상시 확인할 수 있다. 이는 Question을 했다고 해서 Answer이 올 수도 있고, 안 올 수도 있으며, 물어보지도 않았는데 Answer 올 수도 있습니다. 이는 보통 실시간 처리에서 많이 사용이 된다. 예로 들어서 실시간 게임으로 예를 들 수 있다. 또 다른 비슷한 예가 있지만, 방송과 라디오, 음성 통신 등은 TCP 통신에 해당되지 않습니다. 이는 UDP 통신이라고 이야기한다.




4. HTTP의 메세지 종류는 어떻게 구성되고 어떤 역할을 하는지

HTTP 동사라고도 불리는 HTTP 메서드는 HTTP 요청이 쿼리된 서버에서 기대하는 작업을 나타낸다. 예를 들어, 가장 일반적인 두 가지 HTTP 메서드는 'GET'과 'POST'이다. 'GET' 요청은 응답으로 정보를 기대하는 반면(일반적으로 웹 사이트 형식으로) 'POST' 요청은 일반적으로 클라이언트가 웹 서버에 정보를 제출하고 있음을 나타냅니다(양식 정보 등. 예: 제출된 사용자 이름 및 비밀번호). 연락처 양식 작성과 같은 일부 정보를 전송하려는 경우 HTTP PUT 요청을 전송하는식.

HTTP에서 지원하는 요청 메시지는 다음과 같다.
GET: 클라이언트가 서버에게 URL에 해당하는 자료의 전송을 요청한다.
HEAD: GET 요청으로 반환될 데이터 중 헤더 부분에 해당하는 데이터만 요청한다.
POST: 클라이언트가 서버에서 처리할 수 있는 자료를 보낸다. 예를 들어, 게시판에 글을 쓸 때 클라이언트의 문서가 서버로 전송되어야 한다. 멱등성을 보장하지 않는다.

응답코드의 경우
10x : 정보 확인
20x : 통신 성공
30x : 리다이렉트
40x : 클라이언트 오류
50x : 서버 오류



HTTP는 암호화되지 않은 데이터를 전송합니다. 즉, 브라우저에서 전송된 정보를 제3자가 가로채고 읽을 수 있습니다. 이는 이상적인 프로세스가 아니었기 때문에, 통신에 또 다른 보안 계층을 추가하기 위해 HTTPS로 확장되었습니다. HTTPS는 HTTP 요청 및 응답을 SSL 및 TLS 기술에 결합합니다.

HTTPS 웹 사이트는 독립된 인증 기관(CA)에서 SSL/TLS 인증서를 획득해야 합니다. 이러한 웹 사이트는 신뢰를 구축하기 위해 데이터를 교환하기 전에 브라우저와 인증서를 공유합니다. SSL 인증서는 암호화 정보도 포함하므로 서버와 웹 브라우저는 암호화된 데이터나 스크램블된 데이터를 교환할 수 있습니다. 프로세스는 다음과 같이 작동합니다.

사용자 브라우저의 주소 표시줄에 https:// URL 형식을 입력하여 HTTPS 웹 사이트를 방문합니다.
브라우저는 서버의 SSL 인증서를 요청하여 사이트의 신뢰성을 검증하려고 시도합니다.
서버는 퍼블릭 키가 포함된 SSL 인증서를 회신으로 전송합니다.
웹 사이트의 SSL 인증서는 서버 아이덴티티를 증명합니다. 브라우저에서 인증되면, 브라우저가 퍼블릭 키를 사용하여 비밀 세션 키가 포함된 메시지를 암호화하고 전송합니다.
웹 서버는 프라이빗 키를 사용하여 메시지를 해독하고 세션 키를 검색합니다. 그런 다음, 세션 키를 암호화하고 브라우저에 승인 메시지를 전송합니다.
이제 브라우저와 웹 서버 모두 동일한 세션 키를 사용하여 메시지를 안전하게 교환하도록 전환합니다.



5. HTTP와 HTTPS의 관계
HTTP 메시지는 일반 텍스트이므로, 권한이 없는 당사자가 인터넷을 통해 쉽게 액세스하고 읽을 수 있습니다. 반면, HTTPS는 모든 데이터를 암호화된 형태로 전송합니다. 사용자가 민감한 데이터를 제출할 때 제3자가 네트워크를 통해 해당 데이터를 가로챌 수 없음을 확신할 수 있습니다.

HTTP와 비교했을 때 HTTPS의 몇 가지 장점에 대해 알아보겠습니다.

보안
HTTP 메시지는 일반 텍스트이므로, 권한이 없는 당사자가 인터넷을 통해 쉽게 액세스하고 읽을 수 있습니다. 반면, HTTPS는 모든 데이터를 암호화된 형태로 전송합니다. 사용자가 민감한 데이터를 제출할 때 제3자가 네트워크를 통해 해당 데이터를 가로챌 수 없음을 확신할 수 있습니다. 신용카드 세부 정보 또는 고객 개인 정보와 같은 잠재적으로 민감한 정보를 보호하려면 HTTPS를 선택하는 것이 좋습니다.

권위
검색 엔진은 HTTP의 신뢰성이 더 낮기 때문에 보통 HTTP 웹 사이트 콘텐츠의 순위를 HTTPS 웹 페이지보다 낮게 지정합니다. 고객도 HTTP보다 HTTPS 웹 사이트를 더 선호합니다. 브라우저는 브라우저 주소 표시줄에서 웹 사이트 URL 옆에 있는 자물쇠 아이콘을 배치하여 사용자에게 HTTPS 연결을 표시합니다. 사용자는 이러한 추가 보안 및 신뢰 요소 때문에 HTTPS 웹 사이트 및 애플리케이션을 선호합니다.

성능 및 분석
HTTPS 웹 애플리케이션은 HTTP 애플리케이션보다 로드 속도가 더 빠릅니다. 마찬가지로, HTTPS는 참조 링크도 더 잘 추적합니다. 추천 트래픽은 광고 또는 소셜 미디어 백링크와 같은 서드 파티 소스에서 생성되는 웹 사이트 트래픽입니다. 분석 소프트웨어가 신뢰할 수 있는 트래픽 소스를 정확하게 식별하도록 하려면 HTTPS를 활성화해야 합니다.