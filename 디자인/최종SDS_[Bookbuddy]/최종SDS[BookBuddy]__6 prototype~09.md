6\. User interface prototype

이번장에서는 사용자(비회원,회원,관리자)의 인터페이스 프로토타입을
다룬다.

실제 개발된 이미지는 다를있다.

6.1비회원,회원 최초 방문 페이지

<img src="media/image48.png" style="width:6.26042in;height:5.64583in" />

최근 등록된 도서와 도서검색,도서등록,마이페이지,회원가입,로그인이
보인다.

6.2 도서 검색창

<img src="media/image49.png" style="width:6.26042in;height:5.20833in" />

사용자가 도서명,저자,학과를 입력하고 검색할있는 창이다.

6.3회원가입

<img src="media/image50.png" style="width:4.35417in;height:4.07292in" /><img src="media/image51.png" style="width:4.53125in;height:4.65625in" />

회원가입사용자가 학교 메일 닉네임 비밀번호 이름 학번 학년 전화번호 학과
성별등을 입력하여 회원가입한다. 모든 색션이 양식 중복여부 등 조건을
충족시켜야한다.

6.3 도서 등록

<img src="media/image52.png" style="width:5.35417in;height:4.76042in" />

<img src="media/image53.png" style="width:5.1875in;height:2.1875in" />

판매자가등록하는 과정 인터페이스이다.도서명 저자 가격 상태 설명 이미지
등을 등록하는 인터페이스 이다.

6.4 마이페이지

<img src="media/image54.bmp" style="width:5.38333in;height:8.81667in" />  
해당 인터페이스에서는 사용자의 판매 구매 현재 판매하고있는 목록 찜 등
대표적인 정보가 표시된다.

6.5 도서 상세 페이지

<img src="media/image55.bmp" style="width:6.075in;height:6.61667in" />

<img src="media/image56.bmp" style="width:5.67in;height:1.70833in" />

해당인터페이스에서는 책정보 및 구매 구매하기 찜하기 버튼이있다.

6.6 실시간 채팅

<img src="media/image57.bmp" style="width:5.75333in;height:7.21389in" />

구매자와 판매자간의 채팅 창

6.7관리자 로그인

<img src="media/image58.bmp" style="width:6.45833in;height:5.03667in" />

관리자가 관리자 페이지에들어가면 최초로 들어가면 뜨는 인터페이스로
관리자 아이디 비밀번호를 입력하면 관리자 메인 페이지 인터페이스가
나온다. 관리자 회원가입은 없기 때문에 최초에는 마스터아이디 master
비밀번호 1111을 입력해야한다. 로그아웃했을 때 도 이 인터페이스가 나온다.

6.8관리자 메인 페이지

<img src="media/image59.bmp" style="width:5.13667in;height:4.995in" />
관리자 메인 페이지 인터페이스이다. 관리자 추가 대금결제 신고처리 회원
목록 조회 등의 기능으로 접근하기 위한 페이지이다. 관리자 페이지인 만큼
디자인은 없다.

6.9대금 결제

<img src="media/image60.bmp" style="width:6.66667in;height:5.00833in" />

6.10회원목록 조회

<img src="media/image61.bmp" style="width:6.625in;height:4.28333in" />

해당 인터패이스에서는 회원들의 정보 목록을 확인하는 인터페이스 이다.

6.11신고 처리

<img src="media/image62.bmp" style="width:5.14167in;height:2.06903in" />

해당 인터페이스에서는 관리자 3회 이상 신고된 사용자들을 확인하고 강퇴를
할 수 있는 페이지 인터페이스 이다.

6.12 관리자 추가

<img src="media/image63.bmp" style="width:6.66667in;height:6.97292in" />  
해당 인터페이스는 관리자 추가 인터페이스로 관리자를 추가 할 수 있는
페이지 인터페이스 이다.

7\. Implementation requirements

개발요구 준비사항

\- 프로그래밍 언어: Java 17

\- 프레임워크: Spring Boot 3. 이상

\- 데이터베이스: oracle data base server

\- 개발 도구: IntelliJ IDEA, Git

서버로 개발한다면

\- OS: Ubuntu 20.04 or higher

\- RAM: 최소 4GB (8GB 권장)

\- Storage: 50GB SSD

local 로 구현한다면 불필요

사용자

최저사양이상의 노트북

8\. Glossary

admin 관리자

Super Admin 마스터 관리자

9\. References

UI 참고 :

<https://html5up.net/landed>

설계 참고 :

<https://www.daangn.com/kr/>

<https://f-lab.kr/insight/websocket-real-time-chat>

<https://velog.io/@hyeok_1212/%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%B1%84%ED%8C%85-%EC%84%9C%EB%B9%84%EC%8A%A4-%EB%A7%8C%EB%93%A4%EC%96%B4%EB%B3%B4%EA%B8%B0>
