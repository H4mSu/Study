# <center>브라우저와 작동원리
## 브라우저란? 
> 웹 브라우저는 동기적으로 (HTML+CSS),Javascript 언어를 해석하여 내용을 화면에 보여주는 응용 소프트웨어

## 브라우저의 기본 구조
 <img src = "https://d2.naver.com/content/images/2015/06/helloworld-59361-1.png">


1. **사용자 인터페이스** : 검색창, 새로고침, 뒤로가기/앞으로가기 버튼 등 사용자가 접근할 수 잇는 영역
2. **브라우저 엔진** : 사용자 인터페이스와 렌더링 엔진 사이의 동작을 제어
3. **렌더링 엔진** : 브라우저의 **핵심**. 요청한 콘텐츠를 화면에 표시함, HTML과 CSS등을 해석해서 표시하는 엔진
4. **통신** : HTTP 요청 같은 네트워크 호출에 사용, 브라우저마다 독립적인 인터페이스를 가짐
5. **UI 벡엔드** : 기본적인 위젯을 그림, OS 사용자 인터페이스 체계를 사용
6. **자바스크립트 해석기** : 이름 그대로 자바스크립트 코드 해석
7. **자료 저장소** : 자료를 저장하는 계층, Local Storage, Indeced DB, 쿠키 등 브라우저 메모리를 활용하여 저장하는 영역


### 🎬렌더링 엔진 동작 과정
1. **dom 트리 구축을 위한 HTML 파싱** : 브라우저는 서버로부터 HTML 문서를 모두 전달 받음. 렌더링 엔전은 전달 받은 HTML 문서를 파싱해서 *DOM* **트리를 구축**한다. 그리고 **위부 CSS 파일과 스타일 요소도 파싱**한다.
2. **렌더 트리 구축** : *DOM (Document Object Model)* 트리 와 스타일 정보를 합쳐서 렌더 트리를 만든다.
3. **렌더 트리 배치** : 렌더 트리의 각 노드에 대해서 화면 상에서 어디에 배치할 지 결정
4. **렌더 트리 그리기** : UI 백엔드에서 렌더 트리를 그리게 되고, 우리가 보는 화면에 출력 됨
<img src = "https://d2.naver.com/content/images/2015/06/helloworld-59361-3.png">

#### #파싱과 렌더 트리 구축 
 **파싱(parsing)** 이란 코드를 브라우저가 이해할 수있도록 변환 하는 것, 파싱 결과는 보통 문서 구조를 나타내는 노드 트리인 파싱트리/문법 트리이다.

 브라우저는 HTML을 받아서 어휘와 구문을 분석해서 파싱해 **파싱 트리를 만든다**. 파싱 트리를 기반으로 *DOM* 요소와 속성 노드를 가지는 *DOM* 트리를 생성한다. 그리고 DOM을 생성할 떄 거쳣던 과정을 CSS에 만복해서 *CSSOM(CSS Object Model)* 을 생성한다. DOM 트리가 구축 되는 동안 브라우저는 DOM 트리를 기반으로 **렌더트리**를 생성한다. 렌더 트리는 위치와 크기를 가지고 있지 않기 떄문에 **객체들에게 위치와 크기를 결졍** 해주고, 렌더 트리의 각 노드를 화면에 그리면 화면에 콘텐츠가 표현 됨<hr>

 ## 참고 
- https://woong-jae.com/web/210821-how-does-browser-work
- https://bbangson.tistory.com/87
