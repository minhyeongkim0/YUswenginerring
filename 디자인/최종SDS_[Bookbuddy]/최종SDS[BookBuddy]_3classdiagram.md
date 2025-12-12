3\. Class diagram

이번 장은 다양한 관점에서 바라본 Class diagram(CD)과 각각에 대한 설명을
기술한다.

> 각 CD는 시스템 구현 시 고려해야 할 설계 계층별 구성을 나타내며, 실제
> 코드 구조 및 데이터베이스 설계를 직관적으로 파악할 수 있도록
> 작성되었다.

본 문서의 Class diagram을 볼 때 고려해야 할 사항은 다음과 같다.

- 본 시스템의 CD는 웹 서버(백엔드) 와 클라이언트(프론트엔드) 간 데이터
  흐름을 고려하여 설계되었다.

- 웹 애플리케이션용 CD는 목적에 따라 기능(Function), 상속(Inheritance),
  DB 접근(DB Access) 으로 구분된다.

- 각 기능 CD는 하나 이상의 Use Case(사용자 시나리오) 와 직접적으로
  연관되어 있으며,

- 회원가입, 로그인, 도서 등록, 거래 진행, 채팅, 후기 작성 등 실제 사용자
  행위를 기반으로 작성되었다.

각 다이어그램에 대한 간단한 설명은 다음과 같다.

- DB Class Diagram : 데이터베이스의 테이블 구조를 객체 형태로 표현

- 상속 Diagram : 객체 간의 공통 속성과 상속 관계를 표현

- DB 접근 Diagram : DAO 구조를 통한 데이터 접근 계층 설계

- Utility and Static Class : 시스템 전역에서 사용되는 공통 유틸 기능

- 기능 Class Diagram : 주요 기능별 MVC 구조 설계

3.1 DB Class Diagram

> 해당 다이어그램은 데이터베이스(DB)의 관점에서 본 시스템의 구조를 Class
> Diagram 형태로 나타낸다.
>
> ER(Entity Relationship) Diagram을 기반으로 작성되었으며, 실제 테이블
> 간 관계와 데이터 흐름을 객체 단위로 표현하였다.
>
> 본 CD는 사용자(User), 도서(Book), 거래(Trade), 채팅(Message),
> 후기(Review)로 구성되어 있으며,
>
> 시스템의 핵심 데이터가 어떻게 저장되고 연동되는지를 보여준다.
>
> <img src="./images/media/image4.bmp"
> style="width:5.34375in;height:5.10639in" />
>
> \[그림 - \] DB Class Diagram

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>User</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class</p>
<p>Description</p>
</blockquote></td>
<td colspan="3">사이트 이용자 계정 정보 (회원가입, 로그인 정보
저장)</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="12" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td><blockquote>
<p><strong>userId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>사용자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>password</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>사용자 비밀번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>userid</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>사용자를구분하기위한고유의변수</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>name</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>사용자 이름</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>phoneNuber</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>사용자 전화번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>role</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" rowspan="2"><blockquote>
<p>역할(관리자 / 사용자)</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetUserInfo()</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 정보 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>Book</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3">등록된 중고 도서 정보 테이블</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="12" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td><blockquote>
<p><strong>bookId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>도서 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>title</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>도서 제목</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>department</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>학과 / 카테고리</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>price</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>판매 가격</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>condition</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>상태 (하 / 중 / 상 / 최상)</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>sellerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>판매자 id</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>GetBookInfo()</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 상세 정보 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>Trade</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class</p>
<p>Description</p>
</blockquote></td>
<td colspan="3">도서 거래 정보 관리 테이블</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="12" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td><blockquote>
<p><strong>tradeId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>buyerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>구매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>sellerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>판매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>bookId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>도서 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>tradeStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 상태 (판매 중 / 예약 중 / 판매완료)</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>paymentStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>결제 상태 (입금 전 / 입금완료 / 송금완료)</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td><blockquote>
<p><strong>updateStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 상태 변경</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>confirmPayment</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>결제 승인 처리</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 28%" />
<col style="width: 12%" />
<col style="width: 16%" />
<col style="width: 13%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="6"><blockquote>
<p><strong>Message</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="5">1:1 실시간 채팅 메시지 테이블</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td colspan="2" style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td colspan="2" style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="10" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td colspan="2" style="text-align: left;"><blockquote>
<p><strong>messageId</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5"><blockquote>
<p>채팅 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td colspan="2" style="text-align: left;"><blockquote>
<p><strong>senderId</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: left;"><blockquote>
<p>보낸 사람 ID (FK → User.userId)</p>
</blockquote></td>
</tr>
<tr>
<td colspan="2" style="text-align: left;"><blockquote>
<p><strong>receiverId</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: left;"><blockquote>
<p>받는 사람 ID (FK → User.userId)</p>
</blockquote></td>
</tr>
<tr>
<td colspan="2" style="text-align: left;"><blockquote>
<p><strong>content</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: left;"><blockquote>
<p>메시지 내용</p>
</blockquote></td>
</tr>
<tr>
<td colspan="2" style="text-align: left;"><blockquote>
<p><strong>timestamp</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>date</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: left;"><blockquote>
<p>전송 시각</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>SaveMessage()</strong></p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>void</p>
</blockquote></td>
<td colspan="2"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="5" style="text-align: left;"><blockquote>
<p>메시지 저장</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>Review</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3">거래 완료 후 선택형 후기 데이터 저장</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="12" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td><blockquote>
<p><strong>tradeId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>reviewId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>리뷰 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>sellerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>판매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>buyerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>구매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>positiveTag</strong></p>
</blockquote></td>
<td><blockquote>
<p>List&lt;string&gt;</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>선택 가능한 긍정 항목</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>negativeTag</strong></p>
</blockquote></td>
<td><blockquote>
<p>List&lt;string&gt;</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>선택 가능한 부정 항목</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>GetReviewTags()</strong></p>
</blockquote></td>
<td><blockquote>
<p>List&lt;string&gt;</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>결제 승인 처리</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.2 상속 Diagram

해당 다이어그램은 BookBuddy 시스템 내의 주요 객체 간 상속 구조를 나타낸
것이다.

> 시스템 내 역할(Role)별로 공통된 속성 및 동작을 공유하면서, 각 하위
> 클래스가 자신의 책임에 맞게 기능을 확장하는 객체지향(OOP) 기반 구조를
> 표현한다.

<img src="./images/media/image5.bmp"
style="width:6.66667in;height:1.98306in" />

\[그림 - \] 상속 Diagram

크게 두 계층의 상속 구조로 구분된다.

- 사용자 계층 (User Hierarchy)　:　일반 사용자(Member)와 관리자(Admin)

- 거래 계층 (Trade Hierarchy)　:　판매글 거래(SalePost)와 구매
  요청(PurchaseRequest)

이 두 계층은 각각의 공통 속성을 상위 클래스에 정의하고, 하위 클래스에서
개별적인 행동을 추가하여 확장성과 재사용성을 확보할 수 있다.

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>User</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">모든 사용자(회원 및 관리자)의
공통 속성과 메서드를 정의하는 상위 클래스이다.</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="10" style="text-align: center;"><blockquote>
<p>Attribute</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>userId</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>password</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>비밀번호</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>name</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 이름</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>phoneNumber</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>전화번호</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>role</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>역할 (member/admin)</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>Login(id, pw)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 인증 처리</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateInfo(name, phone)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 정보 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetUserInfo()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 기본 정보 반환</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>IsAdmin()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 정보 수정</p>
</blockquote></td>
</tr>
</tbody>
</table>

\- User 계층

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>Admin</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">관리자 계정으로서 거래 관리 및
송금 관련 기능을 수행한다.</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Attribute</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>adminId</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>관리자 식별용 아이디</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ViewCompletedTrades()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Trade&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 완료 내역 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ConfirmPayment(tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>구매자 입금 확인</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>TransferToSeller(tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 송금 완료</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>Member</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">일반 사용자를 의미하며, 도서
등록 및 거래, 후기 작성 등의 일반 기능을 담당한다.</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Attribute</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>myBookList</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Book&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자가 등록한 도서 목록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>myTradeList</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Trade&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>참여 중인 거래 목록</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>RegisterBook()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매글 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ChatWithSeller()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>채팅 요청</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>WriteReview()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>후기 작성</p>
</blockquote></td>
</tr>
</tbody>
</table>

\- Trade 계층

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>Trade</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class</p>
<p>Description</p>
</blockquote></td>
<td colspan="3">거래 관련 클래스의 공통 구조를 정의하는 추상
클래스이다.</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="12" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td><blockquote>
<p><strong>tradeId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>buyerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>구매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>sellerId</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>판매자 아이디</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>bookId</strong></p>
</blockquote></td>
<td><blockquote>
<p>int</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>도서 고유 번호</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>tradeStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 상태 (판매 중 / 예약 중 / 판매완료)</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>paymentStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>string</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>결제 상태 (입금 전 / 입금완료 / 송금완료)</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td><blockquote>
<p><strong>updateStatus</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>거래 상태 변경</p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p><strong>confirmPayment</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3"><blockquote>
<p>결제 승인 처리</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4"><blockquote>
<p><strong>SalePost</strong></p>
</blockquote></td>
</tr>
<tr>
<td><blockquote>
<p>Class</p>
<p>Description</p>
</blockquote></td>
<td colspan="3">판매자가 등록한 도서 판매글 거래를 표현한다.</td>
</tr>
<tr>
<td rowspan="2"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>postDate</strong></p>
</blockquote></td>
<td><blockquote>
<p>date</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>게시글 등록일</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>bookDetails</strong></p>
</blockquote></td>
<td><blockquote>
<p>book</p>
</blockquote></td>
<td><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 대상 도서 정보</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>UpdatePost(condition, price)</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 정보 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeletePost()</strong></p>
</blockquote></td>
<td><blockquote>
<p>void</p>
</blockquote></td>
<td><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매글 삭제</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>PurchaseRequest</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class</p>
<p>Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">구매자가 직접 거래를 요청하는
경우를 표현한다.</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>desiredBook</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>게시글 등록일</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>requestMessage</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 대상 도서 정보</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ApproveRequest()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 승인 처리</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>CancelRequest()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>구매 요청 취소</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.3 DB 접근 Diagram

해당 다이어그램은 DB와 직접 연결되는 데이터 접근 계층(DAO)의 구조를
나타낸다.  
각 DAO 클래스는 테이블 단위로 구성되어 있으며, 데이터의 CRUD(Create,
Read, Update, Delete)기능을 수행한다.  
UserDAO, BookDAO, TradeDAO, MessageDAO, ReviewDAO, AdminDAO등으로
구성되어 있으며  
서비스 로직과 DB 접근 로직을 분리함으로써 코드 재사용성과 유지보수성을
강화한다.

<img src="./images/media/image6.bmp"
style="width:5.48333in;height:4.375in" />

\[그림 - \] DB 접근 Diagram

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>UserDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">회원 정보 테이블(User)에
접근하여 로그인, 회원가입 등의 데이터 처리를 담당하는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="10" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertUser(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>새 사용자 등록 (회원가입)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetUserById(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>User</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>ID로 사용자 정보 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>VerifyLogin(String id, String pw)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>아이디와 비밀번호 검증</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateUser(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 정보 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeleteUser(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>회원 탈퇴 처리</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>BookDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">도서 테이블(Book)에 접근하여
등록, 수정, 삭제 및 검색 기능을 수행하는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="10" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertBook(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateBook(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 정보 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeleteBook(int bookId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 삭제</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetBookById(int bookId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Book</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>특정 도서 상세 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetBooks()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Book&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>전체 도서 목록 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>TradeDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">거래 테이블(Trade)에 접근하여
거래 시작, 상태 변경, 결제 및 완료 처리를 수행하는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertTrade(Trade trade)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>새 거래 생성 (거래 전 상태)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateTradeStatus(int tradeId, String status)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 상태 변경 (전→중→완료)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdatePaymentStatus(int tradeId, String
paymentStatus)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>결제 상태 업데이트</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetTradeById(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Trade</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 상세 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>MessageDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">채팅 메시지 테이블(Message)에
접근하여 1:1 대화 내용을 저장 및 조회하는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertMessage(Message msg)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>채팅 메시지 저장</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetMessagesByUsers(String senderId, String
receiverId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Message&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>두 사용자 간의 대화 불러오기</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ReviewDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">후기 테이블(Review)에 접근하여
선택형 후기(긍정/부정 태그)를 저장하고 불러오는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertReview(Review review)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 완료 후 후기 저장</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetReviewsBySeller(String sellerId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Review&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 후기 목록 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetTagList(String type)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;ReviewTag&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>긍정/부정 후기 태그 목록 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>AdminDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">관리자 전용 기능(입금 확인,
판매자 송금 등)에 필요한 거래 데이터를 조회·갱신하는 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>GetCompletedTrades()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Trade&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 완료 상태의 목록 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ConfirmPayment(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>구매자 입금 확인 처리</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>TransferToSeller(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 송금 완료 처리</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdatePaymentStatus(int tradeId, String status)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>결제 상태 갱신</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.4 Util and Static Classes

<img src="./images/media/image7.bmp"
style="width:5.49333in;height:2.265in" />  
이들은 특정 기능에 종속되지 않고 전역적으로 호출되며, 입력
검증(InputValidator), 날짜 포맷 변환(DateFormatter), 세션
관리(SessionManager), 채팅 통신(ChatHandler), 파일 업로드(FileUploader)
등과 같은 기능을 수행한다.

\[그림 - \] Util and Static Classes

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>InputValidator</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">회원가입 및 도서 등록 시
입력값 형식(아이디, 비밀번호, 전화번호 등)을 검증하는 유틸 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateUserId(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>아이디 형식 검증 (영문+숫자, 4~20자)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidatePassword(String password)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>비밀번호 형식 검증 (8~20자, 특수문자 포함 가능)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidatePhone(String phoneNumber)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>전화번호 숫자 형식 검증 (‘-’ 없이 10~11자리)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateTextField(String text)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>입력 필드의 공백/빈값 여부 확인</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>DateFormatter</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;"><p>도서 등록일, 거래 완료일,
후기 작성일 등을</p>
<p>사람이 읽기 쉬운 날짜 문자열 형식(yyyy-MM-dd HH:mm)으로 변환하는 유틸
클래스</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>Format(Date date)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>날짜 객체를 문자열로 변환</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetToday()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>현재 날짜를 문자열로 반환</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>PadZero(int value)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>한 자리 숫자 앞에 0을 붙여주는 내부 헬퍼 함수</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>SessionManager</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;"><p>사용자 로그인 세션을
관리하는 클래스.</p>
<p>브라우저 종료 또는 로그아웃 시 세션이 만료되며, 로그인 여부를 빠르게
확인하기 위한 공통 관리용 클래스.</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>activeSessions</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Map&lt;String, String&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>현재 로그인된 사용자 세션 목록 (userId → sessionToken)</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>CreateSession(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>로그인 시 세션 생성</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DestroySession(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>로그아웃 시 세션 삭제</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>IsSessionActive(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>세션 유효성 확인</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GenerateToken(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>string</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>내부적으로 고유 세션 토큰 생성</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ChatHandler</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;"><p>WebSocket 기반의 1:1 채팅
기능을 관리하는 정적 클래스.</p>
<p>채팅 서버 연결, 메시지 송수신, 연결 종료 등을 처리.</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>socketConnection</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>object</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>WebSocket 연결 객체</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>OpenConnection(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>WebSocket 연결 생성 (사용자 로그인 시 자동 연결)</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>CloseConnection()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>WebSocket 연결 종료</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>SendMessage(ChatMessage msg)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>메시지 전송</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ReceiveMessage()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>ChatMessage</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>수신 메시지 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.5 기능 Class Diagram

해당 다이어그램은 실제 서비스 기능을 구현하기 위한 기능별 MVC(Model View
Controller) 구조를 표현한다.

주요 기능으로는 회원가입 및 로그인, 도서 등록/수정, 거래 상태 관리, 1:1
채팅, 후기 작성, 관리자, Utility 등이 포함된다.

<img src="./images/media/image8.bmp"
style="width:6.025in;height:5.65in" />

\[그림 - \] 기능 Class Diagram

- 회원가입 / 로그인

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>SignUpController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">회원가입 요청을 처리하는
컨트롤러</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>HandleSignUp(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>입력받은 회원정보를 DB에 전달</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateInput(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>입력 유효성 검사</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>SaveUser(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>회원 데이터 저장</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>LoginController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">로그인 요청을 처리하는
컨트롤러</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>HandleLogin(String id, String pw)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>로그인 요청 처리</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>VerifyCredentials(User user)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>아이디, 비밀번호 검증</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>CreateSession(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>로그인 성공 시 세션 생성</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>UserViewModel</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">현재 로그인된 사용자 정보
유지</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><blockquote>
<p>Attributes</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>currentUser</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>User</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>private</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>현재 로그인한 사용자</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>GetUserInfo()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>User</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 정보 반환</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>Logout()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>세션 종료</p>
</blockquote></td>
</tr>
</tbody>
</table>

- 도서등록 / 수정 기능

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>BookController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">도서 등록, 수정, 삭제 기능
담당</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>RegisterBook(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>새 도서 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>EditBook(int id, String condition, int price)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeleteBook(int id)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 삭제</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ViewBookList()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Book&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>등록된 도서 목록 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>BookLogic</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">도서 관련 비즈니스 로직 수행
(DAO와 연결)</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateBookData(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>등록 데이터 검증</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>SaveBook(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>BookDAO로 저장 요청</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateBook(Book book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>BookDAO를 통해 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeleteBook(int id)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>BookDAO로 삭제 요청</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>BookDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">DB 접근을 통한 도서 CRUD
담당</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="10" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertBook(Book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateBook(Book)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 수정</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DeleteBook(int)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 삭제</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetBookList()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Book&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>전체 목록 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetBookById(int)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Book</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>도서 상세 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

- 채팅

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ChatController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">채팅 UI와 서버 간의 메시지
송수신 관리</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>StartChat(String sellerId, String buyerId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>채팅방 생성</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>SendMessage(ChatMessage msg)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>메시지 전송</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ReceiveMessage()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>ChatMessage</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>메시지 수신</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ChatHandler</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">WebSocket 연결 관리</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="8" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>OpenConnection()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>서버 연결</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>CloseConnection()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>연결 종료</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>Send(ChatMessage)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>메시지 전송</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>Listen()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>ChatMessage</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>서버로부터 수신</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>MessageDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">채팅 내역 저장 / 조회</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertMessage(Message)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>메시지 저장</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetMessagesByUsers(String, String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Message&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>사용자 간 대화 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

\- 거래 관리

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>TradeController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">구매자와 판매자 간 거래 상태
제어</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>StartTrade(int bookId, String buyerId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 시작</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateTradeStatus(int tradeId, String status)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 상태 변경</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ConfirmPayment(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>입금 확인 처리</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>TradeLogic</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">거래 상태 전환에 대한 비즈니스
로직 수행</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateBuyer(String buyerId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 가능 여부 확인</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ChangeStatus(int tradeId, String status)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 상태 변경</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ProcessPayment(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>결제 검증 및 업데이트</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>TradeDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">DB 접근용 거래 정보 관리</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertTrade(Trade)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 생성</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>UpdateTradeStatus(int, String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 상태 변경</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetTradeById(int)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Trade</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>거래 조회</p>
</blockquote></td>
</tr>
</tbody>
</table>

- 후기 작성

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ReviewController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">구매자가 거래 완료 후 선택형
후기를 남김</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ShowReviewOptions()</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;ReviewTag&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>선택 가능한 항목 표시</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>SubmitReview(int tradeId, List&lt;String&gt; pos,
List&lt;String&gt; neg)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>후기 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetSellerReviews(String sellerId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Review&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 후기 목록 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>ReviewDAO</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">후기 데이터 DB 저장 및
조회</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>InsertReview(Review)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>후기 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetReviewsBySeller(String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;Review&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 후기 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>GetTagList(String type)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>List&lt;ReviewTag&gt;</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>선택 가능한 태그 목록 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

- 관리자

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>AdminController</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">거래 완료 후 판매자에게 송금
처리하는 관리자 기능</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ConfirmPayment(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>구매자 입금 확인</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>TransferToSeller(int tradeId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 송금 완료</p>
</blockquote></td>
</tr>
</tbody>
</table>

- Utility

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>InputValidator</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">입력값 검증 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>ValidateUserId(String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>후기 등록</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidatePassword(String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>판매자 후기 조회</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>ValidatePhone(String)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>선택 가능한 태그 목록 반환</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 40%" />
<col style="width: 30%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr>
<td colspan="4" style="text-align: left;"><blockquote>
<p><strong>SessionManager</strong></p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p>Class Description</p>
</blockquote></td>
<td colspan="3" style="text-align: left;">로그인 세션 관리 클래스</td>
</tr>
<tr>
<td rowspan="2" style="text-align: left;"><blockquote>
<p>구분</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Name</p>
</blockquote></td>
<td style="text-align: center;"><blockquote>
<p>Type</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>Visibility</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: center;"><blockquote>
<p>Description</p>
</blockquote></td>
</tr>
<tr>
<td rowspan="6" style="text-align: center;"><blockquote>
<p>Operations</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p><strong>CreateSession(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>세션 생성</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>DestroySession(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>void</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>세션 종료</p>
</blockquote></td>
</tr>
<tr>
<td style="text-align: left;"><blockquote>
<p><strong>IsSessionActive(String userId)</strong></p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>boolean</p>
</blockquote></td>
<td style="text-align: left;"><blockquote>
<p>public</p>
</blockquote></td>
</tr>
<tr>
<td colspan="3" style="text-align: left;"><blockquote>
<p>세션 유효성 검사</p>
</blockquote></td>
</tr>
</tbody>
</table>
