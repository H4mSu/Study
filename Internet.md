# 인터넷 작동 원리
인터넷이란 정보를 담고있는 각 컴퓨터들을 ***TCP/IP 라는 통신 프로토콜***을 이용해 서로 정보를 주고 받도록 한 ***컴퓨터 네트워크***를 말한다.

>**TCP/IP 통신이란?***<BR>
***IP***:네트워크 상에서의 컴퓨터의 고유 주소, 총 4바이트로 이루어짐<br>
***TCP***:클라이언트와 서버간에 데이터를 신뢰성 있게 전달하기 위해 만들어진 프로토콜. 또한 근거리 통신망(LAN),원거리 통신망 (WAN),인트라넷,인터넷등 컴퓨터에서 실행되는 프로그램 간에 일련의 데이터를 안정적으로 순서대로 에러없이 데이터를 교환할수 있게 함.

## 네트워크
<p align = "center">
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdQgzYe%2FbtqTcQXEZmq%2FKb26sNOu1MnNRI9bQONtx1%2Fimg.png"> 두 개의 컴퓨터간의 통신<br>

간단하게 두개의 컴퓨터를 연결할때, 다른사람의 컴퓨터를 ***물리적(케이블)*** 또는 ***무선 (WIFI,BLUETOOTH)*** 등으로 연결해야함<br>



<P align = "center">
    <img src = "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcibDry%2FbtqS29c9Xfw%2FwflLiKKdsMbvar8XbLSVl1%2Fimg.png" width = "400" height= "400"><br>여러개 컴퓨터 연결

      네트워크를 이렇게 연결을 할수잇다. 하지만 복잡해지는것이 단점이다.

<P align = "center">
<img src = "https://mdn.mozillademos.org/files/8445/internet-schema-3.png" width ="400" height="400"><br>라우터 연결<br>

이러한 문제를 해결하기 위해 라우터라는것을 이용한다.
> 라우터 : 특수한 소형 컴퓨터, 단 하나의 작업만을 수행<br>
>>컴퓨터가 A에서 B로 메세지를 보낼려면 A는 메세지를 라우터로,라우터는 메세지를 B에게 보내도록 한다

<P align = "center">
<img src = "https://media.vlpt.us/images/doomchit_3/post/300c095e-770e-4091-bdb7-b17d14c1b691/4.png" WIDTH ="400" HEIGHT ="400" ><br> 라우터: 라우터 연결

<P align = "center">
<img src = "https://media.vlpt.us/images/doomchit_3/post/4676dc11-face-4266-92f2-68f51c38bbe0/internet-schema-5.png" width ="400" height="400"><br> 

이러한 형식으로 컴퓨터와 라우터 , 라우터와 라우터 형식으로 연결함으로써 무한히 확장히 가능하다. <br>
<hr>
하지만 아주 먼곳까지 계속해서 라우터를 유선 케이블로 연결하는 것은 비효율 적이다. 

그리하여 당시 사람들은 **전화선**을 이용하여 장거리 네트워크에 연결하기로 하였다.<br>
네트워크와 전화시설을 연결하기 위해선 **모뎀(MODEM, MOdulator and DEModulater)**라는 장비가 필요하다.

<P align = "center">
<img src = "https://mdn.mozillademos.org/files/8451/internet-schema-6.png" width ="400" height="400"><br>라우터와 모뎀을 연결한 사진

<P align = "center">
    <img src = "https://media.vlpt.us/images/doomchit_3/post/63e641a9-59db-4130-9e96-d97ede4aa3b8/7.png" width = "400" height= "800"><br>라우터와 isp 연결

모뎀을 통해 우리의 네트워크는 전화 시설에 연결된다. 하지만, 아직까지 우리의 컴퓨터가 보낸 메시지가 도달해야 할 컴퓨터(혹은 네트워크)까지 도달하지 않은 상태다.
이 메시지가 전달되려면 인터넷 서비스 제공 업체(ISP, Internet Service Provider) 에 연결되어야 한다.

ISP는 모두 함께 연결되는 몇몇 특수한 라우터를 관리하고 다른 ISP의 라우터에도 액세스할 수 있는 회사이다. 우리나라에는 SK텔레콤, KT, LG유플러스 등이 있다.

따라서 우리 네트워크의 메시지는 ISP 네트워크의 네트워크를 통해 대상 네트워크로 전달된다. 인터넷은 아래 그림과 같이 이러한 전체 네트워크 인프라로 구성된다.

## 참고
- https://velog.io/@doomchit_3/Internet-internet-what-how-IMBETPY
- https://velog.io/@cks3066/%EC%9D%B8%ED%84%B0%EB%84%B7%EC%9D%B8%ED%84%B0%EB%84%B7%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC
- https://development-crow.tistory.com/3