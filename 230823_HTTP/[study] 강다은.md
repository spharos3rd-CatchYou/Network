# http

## http 란

**H**yper**T**ext **T**ransfer **P**rotocol

W3 상에서 정보를 주고받을 수 있는 프로토콜이다. 

- 주로 HTML 문서를 주고받는 데에 쓰인다.
- 주로 TCP를 사용하고 HTTP/3부터는 UDP를 사용하며, 80번 포트를 사용한다.
- 1996년 버전 1.0, 그리고 1999년1.1이 각각 발표되었다.
- HTTP는 클라이언트와 서버 사이에 이루어지는 요청/응답(request/response) 프로토콜이다.
- HTTP는 상태를 갖지 않는(stateless) 프로토콜로, 각 요청은 이전 요청과 독립적으로 처리된다
    
    ⇒  이를 위해 쿠키(cookie)나 세션(session)과 같은 방법으로 클라이언트와 서버 간의 상태 정보를 유지한다
    

참고

클라이언트와 서버 사이에는 프록시가 존재한다

프록시 

- 캐싱 (캐시는 공개 또는 비공개가 될 수 있습니다 (예: 브라우저 캐시))
- 필터링 (바이러스 백신 스캔, 유해 컨텐츠 차단(자녀 보호) 기능)
- 로드 밸런싱 (여러 서버들이 서로 다른 요청을 처리하도록 허용)
- 인증 (다양한 리소스에 대한 접근 제어)
- 로깅 (이력 정보를 저장)

## http의 구조

http는 서버와 클라이언트가 서로 통신하는 구조를 가진다 

![Untitled](https://github.com/spharos3rd-CatchYou/Network/assets/87631575/aaf8db52-33e3-4476-a4ba-196482f091c3)


http와 tcp의 관계

각 노드 간의 연결은 http가 통제 할 수 없다 

단, 전송에서 신뢰할 수 있거나 메시지 손실이 없는(최소한의 오류는 표시) 연결을 요구한다

⇒ 전송 프로토콜 중 신뢰 가능한 프로토콜을 활용해야 한다

- TCP는 신뢰할 수 있는 프로토콜
- UDP는 신뢰성이 떨어지는 프로토콜

HTTP는 연결이 필수는 아니지만 연결 기반인 TCP 표준에 의존합니다.

## http의 메시지 종류 및 구성

http의 메시지는 크게 요청과 응답으로 구성 된다

1. **HTTP 요청(Request)**:
클라이언트가 웹 서버로부터 정보를 요청할 때 보내는 메시지
    - **HTTP 메소드**: GET, POST, PUT, DELETE 등의 요청 유형을 지정
    - **URL(Uniform Resource Locator)**: 요청 대상의 주소
    - **헤더(Headers)**: 요청에 대한 추가 정보
        
        (예: 클라이언트 정보, 캐시 관리 등).
        
    - **바디(Body)**: POST나 PUT과 같은 요청에서 데이터를 전송할 때 사용
    
2. **HTTP 응답(Response)**:
서버가 클라이언트의 요청에 대해 반환하는 메시지
    - **상태 코드(Status Code)**: 요청 처리 결과를 나타내는 숫자 코드
        
         (예: 200 OK, 404 Not Found).
        
    - **헤더(Headers)**: 응답에 대한 추가 정보를 포함
        
         (예: 서버 정보, 캐시 설정 등).
        
    - **바디(Body)**: 응답으로 전송되는 데이터
        
         (예: HTML 문서, 이미지 등).
        

## https와의 관계

서버와 통신을 하는데 있어 중요한 정보는 쿠키와 세션으로 정보를 유지하기에는 보안상의 문제가 생길 수 있다 

⇒ 보안을 위해 HTTPS(SSL 또는 TLS 암호화)를 사용하여 데이터를 암호화하고 인증서를 통해 통신의 신뢰성을 보장할 수 있다.
