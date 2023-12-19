# HTTP

### 1. HTTP - HyperText Transfer Protocol

- HTTP
    - 서버와 클라이언트가 인터넷상에서 요청, 응답으로 데이터를 주고 받기 위한 프로토콜 (web server), 평문 / 80 Port
        - 요청 - Client → Server
        - 응답 - Server → Client
    - 연결을 유지하지 않는 비연결성 프로토콜이기 때문에 요청/응답 방식으로 동작, 응답 후 연결 끊음 (Stateless)
    - 요청이 끝난 후 서버는 클라이언트의 이전 상황을 알 수 없으므로 정보를 유지하기 위해 쿠키와 세션으로 클라이언트 식별
- 특징
    - 주로 HTML 문서를 주고받는데 사용됨
    - 불특정 다수를 대상으로 하는 서비스에 적합
    - 클라이언트와 서버 간 최대 연결 수 보다 많은 요청과 응답 처리 가능
    - TCP/UDP 사용, 80 포트
    - Connectionless - 클라이언트가 서버에 요청을 보내고 서버가 적절한 응답을 클라이언트에 보내면 바로 연결 끊김
    - Stateless - 연결을 끊는 순간 클라이언트와 서버의 통신은 끝나고 상태 정보를 유지하지 않음
- 좋은 점
    - 인터넷이나 다른 네트워크의 다른 프로토콜을 통해 구현될 수 있음
    - 빠르게 액세스 가능하도록 컴퓨터와 인터넷 캐시에 저장됨
    - 플랫폼에 영향받지 않음 → Cross-Platform Porting 가능
    - 방화벽, 글로벌 응용 프로그램에 사용 가능
    - Connected-Oriented 하지 않아서 세션 상태 및 정보를 생성하고 유지하기 위한 네트워크 오버헤드가 없음

### 2. HTTP 동작 방식

- Connect - 클라이언트가 서버에 접속
- Request - 클라이언트가 서버에 요청
- Response & Stateless - 서버가 클라이언트에게 응답 후 연결 끊음

### 3. 요청 데이터 포맷

**헤더 - Request Method, Request URL, HTTP Protocol Version**

- Request Method
    - GET - 정보 요청 (SELECT)
    - POST - 정보를 밀어넣음 (INSERT)
    - PUT - 정보 업데이트 (UPDATE)
    - DELETE - 정보 삭제 (DELETE)
    - HEAD - HTTP 헤더 정보만 요청 → 해당 리소스가 존재하는지, 서버에 문제가 없는지 확인하기 위함
    - OPTIONS - 웹 서버가 지원하는 메소드 종류 요청
    - TRACE - 클라이언트의 요청 반환 → echo 서비스로 서버 상태 확인하기 위함
- Request URL
    - 요청 리소스의 위치 나타냄
- HTTP Protocol Version
    - 웹 브라우저가 사용하는 http protocol version
- 요청 바디
    - POST / PUT 메소드에서 요청할 때 보낼 데이터를 담는 부분
    - GET - 요청할 때 가져가야 하는 리소스를 URL에 붙여서 가져가기 때문에 요청바디가 없음

### 4. 응답 데이터 포맷

- Status Code
    - 1XX 조건부 응답 - 요청 받았음, 작업 계속 함
    - 2XX 성공 - 클라이언트가 요청한 동작을 수신, 이해, 승낙, 처리 성공
    - 3XX 리다이렉션 완료 - 클라이언트가 요청을 끝내기 위해 추가 동작을 해야함
    - 4XX 요청 오류 - 클라이언트에 오류가 있음
    - 5XX 서버 오류 - 서버가 유효한 요청을 수행하지 못했음
        
        ![Screenshot 2023-10-04 at 14.22.25.png](HTTP%20848b9f3732864695a1a0c58f5427db41/Screenshot_2023-10-04_at_14.22.25.png)
        
- 응답 바디
    - 빈 줄 다음에 나오는 것이 실제 응답 리소스 데이터가 나오는 부분
    - 데이터를 요청하고 응답 메세지에 요청한 데이터를 담아서 보내주기 때문에 본문이 있음
    - 응답 메세지에 담긴 HTML을 받아서 브라우저가 화면에 렌더링 함
