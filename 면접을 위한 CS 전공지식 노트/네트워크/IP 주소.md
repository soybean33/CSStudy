# 2.4 IP 주소  
## 2.3.1 ARP(Address Resolution Protocol)
IP 주소에서 ARP를 통해 MAC 주소를 찾아 MAC 주소를 기반으로 통신  
ARP를 통해 **가상 주소인 IP 주소**를 실제 주소인 MAC 주소로 변환  
RARP를 통해 **실제 주소인 MAC 주소**를 가상 주소인 IP 주소로 변환  
장치 A가 장치 B와 통신할 경우, 장치 A가 ARP Requst **브로드캐스트**를 보내 IP 주소에 해당하는 MAC 주소를 찾고, 해당 주소에 맞는 장치 B가 ARP Reply **유니캐스트**를 통해 MAC 주소를 반환하는 과정을 거처 IP 주소에 맞는 MAC 주소를 찾음  

## 2.3.2 홉바이홉 통신  
IP 주소를 통해 통신하는 과정을 홉바이홉 통신이라고 함  
수 많은 서브네트워크 안에 있는 라우터의 라우팅 테이블 IP를 기반으로 패킷을 전달하고 또 전달해 나가며 라우팅을 수행하며 최종 목적지까지 패킷을 전달함  
통신장치에 있는 라우팅 테이블의 IP를 통해 시작 주소부터 시작하여 다음 IP로 계속해서 이동하는 라우팅 과정을 거쳐 패킷이 최종 목적지까지 도달하는 통신  
### 라우팅 테이블(routing table)  
송신지에서 수신지까지 도달하기 위해 사용되며 라우터에 들어가 있는 목적지 정보들과 그 목적지로 가기 위한 방법이 들어있는 리스트  
### 게이트웨이(gateway)  
서로 다른 통신망, 프로토콜을 사용하는 네트워크 간의 통신을 가능하게 하는 관문 역할  

## 2.4.3 IP 주소 체계  
IPv4는 32 비트를 8비트 단위로, IPv6는 64비트를 16비트 단위로 표기  
### 클래스 기반 할당 방식(classful network addressing)  
과거에 사용하던 방식으로 A, B, C, D, E 다섯 개의 클래스로 구분함  
앞 부분을 네트워크 주소, 뒤에 있는 부분을 컴퓨터에 부여하는 주소인 호스트 주소로 사용  
클래스 A, B, C는 일대일 통신, 클래스 D는 멀티캐스트, 클래스 E는 예비용
|클래스|첫 번쨰 바이트|두 번쨰 바이트|세 번쨰 바이트|네 번쨰 바이트|
|--|--|--|--|--|
|A|네트워크|호스트|호스트|호스트|호스트|
|B|네트워크|네트워크|호스트|호스트|
|C|네트워크|네트워크|네트워크|호스트|
|D|브로드캐스트용 주소|
|E|예비용 주소|

사용하는 주소보다 버리는 주소가 많다는 단점이 있고 이를 해소하기 위해 DHCP, IPv6, NAT이 나옴  
### DHCP(Dynamic Host Configuration Protocol)  
IP 주소 및 기타 통신 매개변수를 자동으로 할당하기 위한 네트워크 관리 프로토콜  
대부분의 가정용 네트워크에서 IP 주소를 할당  

### NAT(Network Address Translation)  
패킷이 라우팅 장치를 통해 전송되는 동안 패킷의 IP 주소를 수정하여 IP 주소를 다른 주소로 매핑하는 방법  
NAT으로 공인 IP와 사설 IP로 나눠서 많은 주소를 처리  
여러 대의 호스트가 하나의 공인 IP 주소와 외부에 드러나는 IP 주소를 다르게 유지할 수 있기 때문에 내부 네트워크에 대한 어느 정도의 보안이 가능  
접속하는 호스트 숫자에 따라서 접속 속도가 느려질 수 있음  

## 2.4.4 IP 주소를 이용한 위치 정보  