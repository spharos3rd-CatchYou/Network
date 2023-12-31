# OSI 7계층에 대해

### OSI가 뭐야?
- OSI
    - Open Systems Interconnection의 약자로, 개방형 시스템을 뜻한다
    - 개방이 되어있기 때문에, 누구든지 접근하여 상호 연결 할 수가 있다

### OSI의 7계층의 개요
- 정의
    - 통신이 일어나는 과정을 크게 독립적인 7단계로 구분하여 표준화 한 것
- 중요성
    - 네트워크 구성요소를 표준화 함으로써, 서로다른 네트워크들의 통신을 가능하게 한다
    - 독립적인 7단계로 구분하였기 때문에, 한쪽에 문제가 발생했을 때 다른쪽은 영향을 받지 않는다
    - 컴퓨터 장치나 네트워크 장치, 프로토콜의 표준적인 뼈대를 제공한다

<br>

### OSI 7계층
(* PDU = Protocol Data Unit, 각 계층에서 헤더와 데이터를 합친 부분)


- 상위 계층
    - 7계층 - 응용(Application)
        - 유저가 사용하는 다양한 응용 프로그램, 서비스 및 프로토콜을 제공하는 계층
          <br>
          ex) 웹 브라우저, 이메일, 파일 등
        - 장비 X
        - 프로토콜 : HTTP, FTP, SMTP, DNS, SNMP, SMTP, ...
        - PDU : 데이터(Data)

        <br>

    - 6계층 - 표현(Presentation)
        - 운영체제의 한 부분으로, 입출력되는 데이터를 수.송신에 따라 표현 형태로 전환함
        - 데이터의 인코딩, 디코딩, 암호화, 코드 변환등의 기능
        - 장비 X
        - 프로토콜 : JPEG, MPEG, ASCII, JPG, GIF, ...
        - PDU : 데이터(Data)

    <br>

    - 5계층 - 세션(Session)
        - 프로그램간의 논리적인 연결(세션) 생성 및 제어를 담당
          <br>
          즉, 연결이 끊어지지 않도록 유지시켜주는 역할을 함
        - 세션 생성, 유지, 종료, 복구 등의 기능
        - 장비 X
        - 프로토콜 : SSL, TLS, NetBIOS
        - PDU : 데이터(Data), 메시지(Message)

<br>

- 하위 계층
    - 4계층 - 전송(Transport)
        - 통신을 활성화하는 계층으로, 포트를 열어서 응용 프로그램들이 전송을 할 수 있게 한다
        - 분할/재조립, 연결/흐름제어, 오류제어 등을 수행
        - PDU : TCP면 세그먼트(Segment), UDP면 데이터그램(Datagram)
        - 장치 : 게이트웨이, L4 스위치
        - 프로토콜 : TCP, UDP
        <br>
        (* Q. 일반적으로 웹사이트 접속시 url에 포트번호가 안보이는데 어떻게 된 일일까?)<br>
        (* A. 0 ~ 1023번 포트는 잘 알려진 포트wellknown port라고 해서 고정적으로 사용하는 프로그램들이 있음. 웹의 경우 80번 포트를 사용하고 url 입력시 생략 가능. 사용자가 보기에 url에 포트 번호가 없는 것은 80번 포트임)
        

    <br>

    - 3계층 - 네트워크(Network)
        - 출발지부터 목적지까지 패킷을 주고받을 수 있는 최적의 경로를 IP주소를 이용하여 탐색하는 계층
        - 라우팅, 흐름제어, 세그멘테이션, 오류제어, 인터네트워킹 등을 수행
        - PDU : 패킷 (Packet)
        - 장치 : 라우터, L3 스위치
        - 프로토콜 : IP, ICMP, IGMP, ...

    <br>

    - 2계층 - 데이터링크(Data Link)
        - 수신 : 물리계층에서 받은 정보를, 인접한 두 노드 사이에서 전달하는 계층
        <br>송신 : 네트워크 계층의 데이터를 프레임으로 묶어 전달하는 계층
          
        - 물리적으로 할당받은 MAC 주소를 통해 목적지를 찾아간다
        - 송수신되는 데이터의 오류와 흐름을 관리한다(통신/에러검출/재전송/흐름제어)
        - PDU : 프레임(Frame)
        - 장치 : 브릿지, L2 스위치 등
        - 프로토콜 : Ethernet, Wi-Fi, PPP, FDDI, ...
    
    
    <br>

    - 1계층 - 물리(Physical)
        - 디지털 데이터를, 아날로그 전기 신호로 변환하여 물리적인 전송을 하는 계층
        - 단지 데이터를 전달만 할 뿐, 다른 정보들은 영향을 미치지 않는다
        - PDU : 비트(Bit)
        - 주로 전기적, 기계적, 기능적인 특성을 이용하여 통신 케이블로 신호를 전송한다
        - 장치 : 케이블, 리피터, 허브 등
        - 프로토콜 : X, 전기적 신호를 사용함

<br>

### OSI 7계층에 따른 통신과정
- 송신
    - 상위 계층에서 하위 계층으로 진행(7계층 -> 1계층)
        
        1. 응용(Application) : 송신할 데이터가 생성되고, protocol에 의해 포장됨
        2. 표현(Presentation) : 응용계층에서 전달받은 데이터의 형식을 변환하고, 필요하다면 압축 및 암호화를 진행
        3. 세션(Session) : 표현계층에서 전달받은 데이터의 통신을 시작. 필요하다면 흐름을 제어
        4. 전송(Transport) : 세션계층에서 전달받은 데이터를 세그먼트로 나누고, 포트 번호를 할당함
        5. 네트워크(Network) : 목적지의 IP 주소를 찾아 경로를 결정하고, 데이터에 패킷 헤더를 붙여 패킷으로 바꿈
        6. 데이터링크(Data-Link) : 전달받은 데이터를 프레임으로 묶은 후, 하드웨어 주소(MAC주소)를 할당하고, 오류 검출을 위한 정보를 추가
        7. 물리계층(Physical) : 데이터를 전기적 신호로 바꾸어 물리 장치를 통해 전송이됨

    <br>

- 수신
    - 하위 계층에서 상위 계층으로 진행(1계층 -> 7계층)

        1. 물리계층(Physical) : 전기적 신호로 수신된 데이터를 디지털 데이터로 전환
        2. 데이터링크(Data-Link) : 프레임의 오류 검출 정보를 확인하고, MAC주소를 확인하여 해당 장비에 데이터를 전달함
        3. 네트워크(Network) : 패킷의 헤더를 확인하고, 목적지 IP 주소를 이용하여 데이터를 전달
        4. 전송(Transport) : 포트 번호를 확인하여 데이터를 올바른 프로세스에 전달하고, 세그먼트를 조립
        5. 세션(Session) : 데이터의 통신 흐름을 관리하고, 필요한 경우 통신을 종료
        6. 표현(Presentation) : 데이터 형식을 복원하고, 필요하다면 압축 해제 및 복호화
        7. 응용(Application) : 최종적으로 사용자에게 데이터를 전달하고 표시함
