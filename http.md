# HTTP(Hyper Text Transfer Protocol)란?
텍스트 기반의 통신 규약으로 **인터넷에서 데이터를 주고 받을 수 있는 프로토콜** <br> -> 모든 프로그램이 규약에 맞춰 개발해서 서로 정보를 교환 할 수 있게 됨

# 특징
특징|**초기** | **최근** |
--|--|--|
정보 전송|html 같은 문서를 주로 전송|Plain text, JSON, XML 등 다양한 형태의 정보도 전송하는 애플리케이션 레이어 프로토콜
디자인|웹브라우저와 웹 서버간의 커뮤니케이션 | 모바일 애플리케이션 및 IoT 등과의 커뮤니케이션
<h>

- **비연결성** : 사용자와 서버가 한 번 연결을 맺은 후, 사용자의 요청에 대해 서버가 응답을 마치면 맺었던 연결을 끊어버리는 성질
     - 장점 : 매번 연결을 유지할 필요가 없기 때문에 리소스를 줄일수 있어 더 많은 연결을 그때 그때 수행 할 수있다.
     - 단점 : 연결 해제를 매번 해줘야 하기 때문에 이에 대한 오버헤드가 일어남
- **무상태 프로토콜** : 서버가 두 요청 간에 어떠한 상태나 데이터를 유지하지 않음을 의미
- 일반적으로 안정적인 **TCP/IP 레이어**를 기반으로 사용하는 응용 프로토콜
    > **TCP/IP란?** TCP 와 IP를 합쳐서 부른말.<br>
    IP주소 체계를 따르고 IP Routing을 이용해 목적지에 도달하며<br>
    TCP 특성을 활용해 송신지와 수신자의 논리적 연결을 생성하고 신뢰성을 유지할 수 있도록 하겠다는 것을 의미
- **확장 가능하다** : 클라이언트와 서버가 새로운 헤더의 시맨틱에 대해서만 합의한다면, 언제든지 새로운 기능을 추가 할 수 있다.

# HTTP 동작
사용자가 브라우저를 통해 서비스를 URL을 통하여 다른 것을 통해 요청(request) <br> 서버에서는 해당 요청사항에 맞는 결과를 찾아서 사용자에게 응답(response)
<p align = "center">
<img src = "https://t1.daumcdn.net/thumb/R720x0.fpng/?fname=http://t1.daumcdn.net/brunch/service/user/5xeg/image/NVuAaSpIy-Daj2PFxim0DrT84rg.png" weight = "300px" height = "200px"> <br>HTTP 작동 방식
</p>

# 요청(Request)
<p align = "center">
<img src = "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc7mI3U%2FbtqWX45M76d%2FgGoVLK6rcUJhekrxMcq6a1%2Fimg.png">
</p>

**1번줄** : method를 맨 앞에 적고 그 뒤에는 path , 그 뒤에는 프로토콜의 종류 와 버젼을 적음(GET/HTTP/1.1)<br>
**2번 줄 이후** : HTTP Request Header 부분<br>
**2번줄** : 리소스를 요청하는 경로, 요청하고자 하는 서버의 도메인을 적음, 예시에서 포트번호가 생략된것은 80번 포트(http의 기본포트)이기 때문

## HTTP 요청 method
- **GET** : 특정 리소스를 받기 위한 요청 ∴ 리소스의 생성, 수정 및 삭제 등에 사용 해선 안됨
- **POST** : 리소스를 생성하거나 컨트롤러를 실행하는데 사용
- **PUT** : 변경 가능한 리소스를 업데이트 하는데 사용되며 항상 리소스 식별 정보를 포함해야함
- **DELETE** : 특정 리소스를 제거하는데 사용
    - 일반적으로 Request body가 아닌 URL 경로에 제거하려는 리소스의 ID를 전달
- **PATCH** : 변경 가능한 리소스의 부분 업데이트에 사용되며 항상 리소스 식별 정보를 포함해야 한다.
    - PUT을 사용해 전체 객체를 업데이트 하는 것이 관례여서 거의 사용X

- **HEAD** : 클라이언트가 본문 없이 리소스에 대한 헹더만 검색하는 경우 사용
     - 일반적으로 클라이언트가 서버에 리소스가 있는 지 확인하거나 메타 데이터를 읽으려는 때만 GET 대신 사용
- **OPTION** : 클라이언트가 서버의 리소스에 대해 수행 가능한 동작을 알아보기 위해 사용
    - 일반적으로 서버는 이 리소스에 대해 사용할 수 있는 HTTP 요청 메서드를 포함하는 Allow 헤더를 반환

# 응답 (Response)
<p>
<img src = "https://kyun2da.dev/static/94e095a3fcf89fd3e3fd792d5de89ba2/c8e86/http_response.png">
</p>

1. HTTP 프로토콜 버젼
2. 상태코드
3. 상태메세지
4. HTTP 헤더
5. body

## 🛠 상태 코드
모두 숫자 세 자리로 이루어져 있음
- **1XX(조건부 응답)** : 요청을 받았으며 작업을 계속한다
- **2XX (성공)** : 사용자가 요청한 동작을 수신하여 이해했고 승낙했으며 성공적으로 처리했음을 가리킴
- **3XX(리다이렉션 완료)** : 사용자는 요청을 마치기 ㅜ이해 추가 동작을 취해야 한다.
- **4XX (요청 오류)** : 사용자에 오류가 있음을 나타냄
- **5XX(서버 오류)** : 서버가 유요한 요청을 명백하게 수행하지 못했음을 나타냄

# 참고
- https://velog.io/@surim014/HTTP%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80
- https://kyun2da.dev/CS/http%EB%9E%80/
- https://surprisecomputer.tistory.com/54
- https://aws-hyoh.tistory.com/entry/TCPIP-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0