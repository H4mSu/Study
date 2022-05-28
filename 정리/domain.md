# 도메인이란?
### 도메인이란??
ip는 사람이 이해하고 기억하기 어렵기 때문에 이를 위해서 각 ip에 이름을 부여할 수 있게 했는데, 이것을 도메인이라고 한다.
<p align= center>
<img src="https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/121/298.png" width="300px">

- opentutorials.org -> 115.68.24.88
- naver.com -> 220.95.233.172
- daum.net -> 114.108.157.19

### 도메인 네임의 구조
<p align= center>
<img src ="https://velog.velcdn.com/images%2Fm-vault%2Fpost%2Faa47ab6d-b47e-4150-b23d-4feb79d20924%2F1.png" width="400px">

1. **Root**<BR>
 가장 최상위에 위치해있다.<BR>
 실제로 주소엔. 이 있으나, 생략된 형태로 사용해도 무방함

2. **TLD(최상위 도메인)**<BR>
도메인 레벨 중에 가장 높은 단계에 있는 도메인

3. **SLD(second-Level Domain, 차상위 도메인)**<BR>
‘www.google.co.kr’ 처럼 SLD가 존재하는 경우도 있고, ‘www.naver.com’ 처럼 SLD가 존재하지 않고 TLD에서 바로 도메인 이름으로 건너뛰는 경우도 있음.<BR>추가로, **com**은 commercial을 의미하므로 굳이 **co.com** 같은 형태로 쓸 필요가 없으며, **go.com** 같은 경우 의미상 모순을 이루게 됨.
4. **SUB(도메인 이름)**<BR>
    임의로 지정할 수 있는 사이트의 이름<BR>
->  google,naver,daum 등이 도메인 이름 부분
5. **www** <BR>
world wide web의 약자로, 도메인 네임에 포함되지 않는 '호스명'
SLD은 쓸 수도, 생략할 수도 있기 때문에 도메인 구조를 단계로 나눴을 때, 'www.google.co.kr'처럼 3단계 구조일수도 있고
'www.naver.com'처럼 2단계 구조가 될 수도 있다.

## 참고
- https://velog.io/@m-vault/%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%84%A4%EC%9E%84%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94