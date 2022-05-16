# DNS와 작동원리
## DNS(Domain Name System)
호스트의 도메인 이름을 호스트의 네트워크 주소로 바꾸거나 그 반대의 변환을 수행할 수 잇도록 하기 위해 개발된 시스템

IP 주소와 사람이 읽을 수 있는 형태인 도메인 이름 부분에서 나온 그 도메인을 다시 IP 주소로 반환해주는 과정을 담당하는 시스템
- **IP 주소** : 웹의 하나뿐인 특정 위치를 나타냄 (172.217.161.206같은 숫자덩어리)
- **도메인 이름 서버**: 브라우저에 입력하는 웹주소(google.com)를 웹사이트이 실제 (IP) 주소에 맞춰주는 특별한 서버

## DNS 구성요소
1. **도메인 네임 스페이스(Domain Name Space)**: 최상위에 루트 DNS 서버가 존재하고, 그 하위로 인터넷에 연결된 모드 노드가 연속해서 이어진 계층 구조로 구성

2. **네임 서버(Name Server)**: 주소를 변환 시키기 위해 도메인 네임 스페이스의 트리구조에 대한 정보가 필요. 이 정보를 가진 서버 도메인 이름을 IP주소로 변환하는 것을 네임 서비스
3. **리졸버(Resolver)**: DNS클라이언트의 요청을 네임 서버로 전달하고 네임 서버로부터 도메인 이름과 IP 주소를 받아 클라이언트에게 제공하는 기능을 수행

## 도메인 네임 특징
- Kr : 각 국가별 사용을 위해 정의한 도메인으로 (ISO 3166 [4]에서 정의하는 국가 코드에 기반)
- com : 기업과 같은 상용 조직을 위한 도메인
- edu : 교육 기관들을 위한 도메인
- net : 네트워크 서비스 제공자와 관련된 시스템을 위한 도메인
- org : 다른 TLD에 속하지 않는 비정부 단체를 위한 도메인
- int : 국제 협약에 의해 만들어짂 조직을 위한 도메인
- gov : 본래 정부 기관이나 단체를 위한 도메인이었으나, 현재 미국의 주 정부를 비롯한 연방 정부만 등록하도록 결정
- mil : 미국 국방성 관련 기관에서 사용하도록 정의한 도메인
- arpa : IP 주소를 도메인 이름으로 매핑하기 위해 사용되는 특수 도메인

## 🎬 DNS 동작원리
<p align = "center">
<img src ="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcgbNqc%2Fbtq1uuMDN4D%2Fcfifchk6rOn14ZyP9LB8O0%2Fimg.jpg" >작동원리

1. DNS Query (from **Web Browser** to **Local DNS**) <Br> : "제가 원하는 웹 사이트의 IP 주소를 알고 계신가요?" Local DNS 서버에게 전달
2. DNS Query (from **Local DNS** to **Root DNS**)<br> :  "제가 원하는 웹 사이트의 IP 주소를 알고 계신가요?" Root DNS서버에게 전달
    > - 로컬 DNS서버는 Root DNS 서버 정보를 가지고 있어야함
    > - Root DNS 서버는 전세계에 13대 구축되어 있음. 우리나라의 경우 Root DNS 서버가 구축 되어있지는 않지만 Root DNS 서버에 대한 미러 서버를 3대 운용하고 있다.
3. DNS Response (from **Root DNS** to **Local DNS**) <br>: "저는 모르지만 , Com 도메인을 관리하는 네임서버의 이름과 IP 주소를 알려드릴 테니 거기에 물어보세요"
4. DNS Query (from **Local DNS** to **com NS**) <br>: “ 안녕하세요. www. naver. com의 IP 주소를 알고 계신가요?"

5. DNS Response (from **com NS** to **Local DNS**)<br> : "저는 모르지만 , Com 도메인을 관리하는 네임서버의 이름과 IP 주소를 알려드릴 테니 거기에 물어보세요"
6. DNS Query (from **Local DNS** to **naver. com NS**)<Br> : “ 안녕하세요. www. Naver .com의 IP 주소를 알고 계신가요?"
7. DNS Response (from **naver .com NS** to **Local DNS**) <br>: "저는 모르지만 해당 웹은 www. g.naver. com이라는 이름으로 통해요. g.naver .com 도메인을 관리하는 네임서버의 이름과 IP 주소를 알려드릴테니 거기에 물어보세요"
8. DNS Query (from **Local DNS** to **g.naver. com NS**)<br> : “ 안녕하세요. www. g.naver. com의 IP 주소를 알고 계신가요?"
9. DNS Response (from **g.naver .com N**S to **Local DNS**)<br> : " 네 www. g.naver .com의 IP 주소는 222.222.222.22와 333.333.333.33입니다"
10. DNS Response (from **Local DNS** to **Web Browser**) <br>: "네 www. naver .com의 IP 주소는 222.222.222.22와 333.333.333.33입니다"

### TLD(Top-Level Domain)
.com 도메인을 관리하는 서버
<img src ="https://velog.velcdn.com/images%2Fgoban%2Fpost%2F679d8a2b-1933-4850-95b9-c13765b9ff6c%2FTLD.jpg">

※velog.io 와 github.io (깃허브 블로그)는 영국령 인도양 지역의 인터넷 국가 코드 최상위 도메인이다. io 도메인을 쓰면 기존 com, net이 점유하고 있던 도메인들을 벗어나 새롭게 도메인을 확보할 수 있다고 한다

### 출처
- https://velog.io/@goban/DNS%EC%99%80-%EC%9E%91%EB%8F%99%EC%9B%90%EB%A6%AC
- https://ja-gamma.tistory.com/entry/DNS%EA%B0%9C%EB%85%90%EB%8F%99%EC%9E%91%EC%9B%90%EB%A6%AC
- https://kkoon9.tistory.com/69
- https://is-this-it.tistory.com/43