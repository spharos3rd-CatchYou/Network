# 네트워크 스터디 08/28

네트워크는 크게 서비스를 받는 입장과 서비스를 제공하는 입장으로 나뉜다.  
<서비스를 받는 입장>   
집에서 인터넷 접속하는 경우, 회사에서 인터넷에 접속해 업무를 하는 경우  
<서비스를 제공하는 입장>  
클라우드, 데이터센터, 회사 기계실에 서버를 놓고 서비스를 제공하는 경우  

→ 네트워크에 접속한 구성원 수, 필요한 네트워크의 속도에 따라 여러 가지 상황 고려  

◆ 홈 네트워크 구성  
인터넷 – 케이블 – 모뎀(네트워크장비) – 케이블 – 공유기 – 케이블/매체 – 단말기  
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/f5b3ad00-278b-4e00-8732-c7f08a61c55c)

우리집 예시  
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/3d3c62ca-b5b0-470f-ac51-2b16d1d6ab3e)

 
◆ 데이터 센터 네트워크  
고속 이더넷 기술 사용  
① 안정적이고 빠른 대용량 서비스 제공을 목표로 구성

※ 이더넷 기술  
LAN, WAN 등의 네트워크 환경에서 각 기기들이 전송매체를 통해 데이터를 주고받을 수 있도록 만들어진 기술  
→ CSMA/CD 프로토콜 사용(호스트가 채널의 상태를 감지하여 충돌을 회피하는 네트워킹 방식)  

10G, 25G, 40G, 100G, 400G 등은 데이터 전송 속도를 나타낸다. 여기서 "G"는 기가비트(Gigabit)
ex)10G: 10 기가비트 전송 속도를 의미한다. 10G 이더넷은 10 기가비트 데이터를 1초 동안 전송할 수 있는 기술을 말함

② 다양한 이중화 기술을 사용, 높은 통신량을 수용할 수 있어야 함

※ 이중화 기술이란?  
시스템의 장애를 대비하는 등 안정성을 강화하기 위해 같은 시스템을 두 벌 또는 그 이상으로 만들어 두고 하나의 시스템에 장애가 생겼을 때 즉시 다른 시스템으로 전환 되도록 만들어진 구조    
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/be31059f-53af-4334-8791-d60a0fae7069)


③ 기존엔 3계층 구성이 일반적이었으나 가상화 기술과 높은 대역폭을 요구하는 스케일 아웃 기반의 애플리케이션과 서비스가 등장하면서 2계층 구성인 스파인-리프 구조로 변화함  

※ 스케일 아웃(Scale-out)은 인프라를 업그레이드하는 방법 중 하나로 장비를 추가해서 확장하는 방식  
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/7fbc76ef-9ae6-487c-b2f0-ace8beaf0d5a)
 
## 프로토콜
통신할 때의 규약  
물리적 측면: 데이터 전송 매체, 신호 규약, 회선 규격 등. 이더넷이 널리 쓰임  
논리적 측면: 장치들끼리 통신하기 위한 프로토콜 규격. TCP/IP가 널리 쓰임  

→ 1900년대(네트워크 서비스들이 처음 개발되었던 때)에는 적은 컴퓨팅 자원과 매우 느린 네트워크 속도를 이용해 최대한 효율적으로 통신하는 것이 목표여서 2진수 비트 기반으로 프로토콜이 만들어짐  
→ 애플리케이션 레벨의 프로토콜은 문자기반 프로토콜이 많이 사용된다.  
Ex) HTTP, SMTP  
→ 문자로 표현함으로 사람도 읽을 수 있다.  
→ 실제 텍스트 파일과 같은 데이터가 전달되어 효율성은 비트 기반 프로토콜보다 떨어지지만 다양한 확장이 가능  
 
TCP/IP는 별도 계층에서 동작하는 프로토콜이지만 함께 사용하기 때문에 이런 프로토콜 묶음(집합)을 프로토콜 스택이라고 부른다.  
→ TCP, IP 이외에도 UDP, ICMP, ARP, HTTP, SMTP, FTP등 다양한 애플리케이션 레이어 프로토콜들이 있다.  
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/e98f69d1-2118-4bb9-96e4-2f5a3fd80bf4)

 
 
## OSI 7계층과 TCP/IP 스택

→ 과거에는 통신용 규약이 표준화되지 않았고 각 벤더에서 별도로 개발했기 때문에 호환되지 않는 시스템이나 애플리케이션이 많았고 통신도 불가능 했다.  
→ 이를 하나의 규약으로 통합하려는 노력이 OSI 7계층에 남아 있다.  
→ 다만 OSI 7계층은 네트워크의 주요 레퍼런스 모델로 활용되고 있지만 현재 대부분의 프로토콜은 TCP/IP 프로토콜 스택 기반으로 되어 있다.  

 ![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/fc5d1ab1-b077-46d8-9973-e94769d3763e)

→ 계층을 나누면 복잡한 데이터 전송 과정을 이해하기 쉽다.  
→ 네트워크 프로토콜을 전부 개발하는 대신 계층별로 프로토콜을 개발해 네트워크 구성요소들을 모듈화 할 수 있다.  
→ 계층 분류는 계층의 역할과 목표에 따른 것인데 이로 인해, 애플리케이션 개발자는 하위 데이터 플로 계층을 크게 고려하지 않고, 네트워크 엔지니어는 애플리케이션 계층을 크게 고려하지 않는다.  
→ 이런 이유로 애플리케이션 개발자는 하향식으로 네트워크를 바라보고 네트워크 엔지니어는 상향식으로 네트워크를 인식함.  

TCP/IP는 모델은 이론보다 실용성에 중점을 둔 프로토콜로, 4개의 계층으로 구분함.  
![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/f0b87aab-f837-4aeb-a9f3-91f0759da8f6)
 

### OSI 각 계층별 설명
#### ◆ 1계층(피지컬 계층)  
물리적 연결과 관련된 정보를 정의  
전기 신호를 전달하는 역할  
주요 장비: 허브, 리피터, 케이블, 커넥터, 트랜시버, 탭 등  
→ 전기신호가 1계층 장비에 들어오면 이 전기 신호를 재생성 해 내보냄  
→ 주소 개념이 없으므로 전기 신호가 들어온 포트를 제외하고 모든 포트에 같은 전기신호를 전송  

#### ◆ 2계층(데이터 링크 계층)  
전기신호를 모아 우리가 알아볼 수 있는 데이터 형태로 처리    
주소 정보를 정의하고 정확한 주소로 통신이 되도록 하는데 초점    
→ 출발지, 도착지 주소 확인, 내게 보낸 것이 맞는지, 내가 처리해야 하는 지 등 검사     
데이터에 대한 에러 탐지, 고치는 역할도 수행    
받는 사람이 현재 데이터를 받을 수 있는지 확인작업(플로 컨트롤)  
2계층에서 동작하는 네트워크 구성 요소: 네트워크 인터페이스 카드, 스위치  
2계층의 가장 중요한 특징이 MAC주소라는 주소체계가 있다는 것인데 두 구성요소 모두 MAC 주소를 이해할 수 있고, 스위치는 MAC주소를 보고 통신해야 할 포트를 지정해 내보내는 능력이 있다.  

※MAC 주소: 물리주소, 전세계에서 유일한 번호로 할당, 48비트 숫자로 구성, 앞 24비트는 랜카드를 만든 제조사 번호, 뒤쪽 24비트는 제조사가 붙인 일련번호 

 ![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/1a000220-9d0b-4ad5-8f10-1d1276f34f62)

#### ◆ 3계층(네트워크 계층)
IP주소와 같은 논리적인 주소가 정의된다.  
장비: 라우터 - IP주소를 사용해 최적의 경로를 찾고 해당 경로로 패킷을 전송하는 역할  

#### ◆ 4계층(트랜스포트 계층)
실제로 해당 데이터들이 정상적으로 잘 보내지도록 확인하는 역할  
데이터를 분할해 패킷에 실어 보내다 보면 중간에 패킷이 유실되거나 순서가 바뀐 것을 바로잡아주는 역할  
장비: 로드 밸런서, 방화벽  

#### ◆ 5계층(세션 계층)
양 끝단의 응용 프로세스가 연결을 성립하도록 도와주고 연결이 안정적으로 유지되도록 관리하고 작업 완료 후에는 이 연결을 끊는 역할  
에러로 중단된 통신에 대한 에러 복구와 재전송도 수행  

#### ◆ 6계층(프레젠테이션 계층)
표현방식이 다른 애플리케이션이나 시스템 간의 통신을 돕기 위해 하나의 통일된 구문 형식으로 변환시키는 기능을 수행  
일종의 번역기, 변환기 역할 수행  
→MIME 인코딩, 암호화, 압축, 코드 변환 등 수행  

#### ◆ 7계층(애플리케이션 계층)
애플리케이션 프로세스를 정의하고 애플리케이션 서비스를 수행  
사용자 입/출력 정의 등  

 
## 인캡슐레이션과 디캡슐레이션

![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/794cb47c-2af4-4115-a837-e10a32acf235)
 
4계층 ~ 1계층은 한 계층씩 내려갈 때 헤더를 붙여서 내려 보낸다.  
1계층 ~ 4계층은 헤더 정보를 벗겨내고 올려보낸다.  

캡슐화하는 과정에서 헤더에 넣는 정보가 매우 많은데   
두가지 정보가 반드시 포함되어야 한다.   
1.현재 계층에서 정의하는 정보  
→ 데이터를 잘 분할하고 받는 쪽에서 잘 조립하기 위해  
2.상위 프로토콜 지시자  
→ 디캡슐레이션하는 목적지 쪽에서 헤더에 정보가 없으면 어떤 상위 프로토콜로 올려보내 주어야 하는지 결정할 수 없는 문제가 생김  

 
## 네트워크 연결 구분  
네트워크 규모와 관리 범위에 따라 LAN, MAN, WAN 3가지로 구분  
### ◆ LAN – Local Area Network의 약자  
홈 네트워크용과 사무실용 네트워크처럼 비교적 소규모의 네트워크  
자신이 소유한 건물이나 대시에 직접 구축한 선로로 동작시키는 네트워크  

### ◆ WAN – Wide Area Network의 약자
먼 거리에 있는 네트워크를 연결하기 위해 사용  
원격지 연결을 위해 통신사업자(SKB, KT, LGU+)로부터 빌려 쓰는 네트워크   

※MAN은 한 도시 정도를 연결하고 관리하는 네트워크  
→ 통신사가 이미 갖고 있는 인프라 기반으로 네트워크를 구축하면 WAN, 자체 인프라를 통해 네트워크를 구축하면 MAN으로 구분


## 네트워크 회선
### ◆ 인터넷 회선
인터넷 접속을 위해 통신사업자와 연결하는 회선  
일반가정에서는 가입자와 통신사업자 간에 직접 연결되는 구조가 아니라 전송 선로 공유 기술을 사용한다.  
Ex) 아파트 광랜은 아파트에서 통신사업자까지 연결한 회선을 아파트 가입자가 공유하는 구조  
→ 주변 사용량에 따라 속도가 달라짐(사용자 최대 속도를 보장하지 않음)  
종류: 광랜, FTTH, 동축 케이블 인터넷, xDSL 등  

### ◆ 전용 회선
가입자와 통신사업자 간에 대역폭을 보장해주는 서비스   
가입자와 통신사업자 간에 전용케이블로 연결되어 있고 통신사업자 내부에서 TDM같은 기술로 직접 연결한 것처럼 통신 품질 보장  
전용 회선을 가입자와 접속하는 전송 기술을 기반으로 구분한다면?  
저속: 음성 전송 기술 기반  
→ 작은 기본 단위를 묶어 회선접속 속도를 높이는 방법  
→ 높은속도가 필요하지 않을 때나 높은 신뢰성이 필요할 때 사용  
→ 기술 사용을 위해서는 원격지 전송 기술로 변환할 수 있는 라우터가 필요  

고속: 메트로 이더넷  
→ 고속 연결은 대부분 광케이블 기반의 이더넷을 사용  
→ 가입자 - 통신사업자 간의 접속은 이더넷 사용, 통신사업자 내부는 다른 고속 통신 기술을 사용


### ◆ 인터넷 전용 회선
인터넷 연결 회선에 대한 통신 대역폭을 보장해주는 상품  
가입자가 통신사업자와 연결되고 이 연결이 다시 인터넷과 연결되는 구조  
이더넷 기술이 가장 많이 쓰임  

### ◆ VPN
물리적으로 전용선은 아니지만 가상으로 직접 연결한 것 같은 효과가 나도록 만들어주는 네트워크 기술  

#### 1.통신사업자 VPN
비용 낭비를 줄이고 먼 거리와 연결하더라도 비용을 줄이기 위해 통신사업자가 직접 가입자를 구분할 수 있는 VPN기술을 사용  
대표적인 기술: MPLS VPN  
→ 여러 가입자가 하나의 MPLS 망에 접속되지만 가입자를 구분할 수 있는 기술을 적용해 전용선처럼 사용  
→ 여러 가입자가 하나의 망에 접속해 통신하므로 공용 회선을 함께 이용하게 되어 비용이 낮아진다.
→ 본사-지사, 지사-지사간연결 등에 사용  

#### 2.가입자 VPN
일반사용자의 경우 대부분 가입자 VPN 사용  
일반 인터넷망을 이용해 사용자가 직접 가상 전용 네트워크를 구성  

요약하면, 통신사업자 VPN은 기업이나 조직 간의 안전한 데이터 통신을 위한 서비스로 대규모 네트워크에서 사용되며,   
가입자 VPN은 개별 사용자가 안전한 연결을 유지하고 인터넷을 통해 가상 사설 네트워크에 접속하기 위한 서비스  


### ◆ DWDM(파장 분할 다중화)
하나의 광케이블에 다른 파장의 빛을 통해 여러 채널을 만드는 동시에 많은 데이터를 전송  
먼 거리를 통신할 때 케이블 포설 비용이 매우 많이 들고 관리가 어려운 문제를 극복하기 위해 개발되었다.  
WDM기술이 나오기 전에는 하나의 광케이블에 하나의 통신만 가능해 여러 개의 케이블을 포설해야 했고 어려움이 있었다.  
→ 기가 인터넷에서 많이 사용  

※ 기가 인터넷  
FTTH(광 섬유를 집안까지 연결한다는 뜻, 인터넷을 바로 공급 받을 수 있어 속도 안정적, 품질 우수)가 사용 되고 구축방식에 따라  
PTP: 가입자와 통신사업자 간에 케이블을 직접 포설  
AON: 광신호 분리장비에 전기가 필요한 스위치와 같은 장비가 사용된다.  
PON: 전기 인입 없이 광신호를 분리해 가입자와 통신사업자 간의 케이블을 줄임  

![image](https://github.com/spharos3rd-CatchYou/Network/assets/120145637/99475752-79cc-4ec8-a2fd-b2ece5dfb72d)

#### <참고>
https://tecoble.techcourse.co.kr/post/2021-10-12-scale-up-scale-out/  
https://ensxoddl.tistory.com/219
 
