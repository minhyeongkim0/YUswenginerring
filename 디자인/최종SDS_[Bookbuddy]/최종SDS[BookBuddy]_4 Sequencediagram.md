4\. Sequence diagram

4.1 회원가입

<img src="./images/media/image10.png"
style="width:5.90556in;height:5.13917in" />

사용자가 시스템에 회원가입하는 과정을 나타내는 sequence diagram이다.
사용자가 회원가입을 누르면 회원가입 화면이 나온다. 사용자가 화면에 학교
이메일을 입력한 후 인증하기를 누르면 해당 이메일로 인증번호가 발송된다.
발송된 인증번호를 인증번호 확인란에 입력 후 인증확인을 누르면 정상적으로
인증이 완료된다. 닉네임을 입력한 후 중복확인 버튼을 눌러서 중복확인을
검사한다. 비밀번호와 비밀번호 재확인란에 동일한 비밀번호를 입력한 후
동일한 경우만 진행가능하다. 그 후에 화면에 이름, 학번, 학년, 전화번호,
학과, 성별을 입력하고 제출하기 버튼을 누르면 서버에 회원가입 요청을 하고
응답을 받으면 로그인 화면으로 전환된다

4.2이메일 인증

<img src="./images/media/image11.png"
style="width:5.90556in;height:2.81403in" />

SignUpController가 이메일 인증을 요청하면 EmailService로 전달되며,
UtilService가 랜덤한 인증 코드를 생성한다. 생성된 인증 코드는
EmailService를 통해 사용자의 이메일로 발송된다. 동시에, 생성된 인증
코드는 RedisService를 통해 Redis에 안전하게 저장되어 이후 인증 확인에
사용할 수 있도록 관리된다. 최종적으로 이메일 전송이 완료되면 컨트롤러에
응답을 반환한다.

4.3 로그인

<img src="./images/media/image12.png"
style="width:5.90556in;height:3.10014in" />

4.4 로그아웃

<img src="./images/media/image13.png"
style="width:5.90556in;height:2.71264in" />

4.5 도서 등록

<img src="./images/media/image14.png"
style="width:5.90556in;height:3.6075in" />

4.6 도서검색

<img src="./images/media/image15.png"
style="width:5.90556in;height:3.52444in" />

사용자가 키워드와 필터 조건(판매 상태, 도서 상태 등급, 가격 범위)을
입력하여 도서를 검색한다. SearchService가 검색 쿼리를 생성하고
BookRepository를 통해 데이터베이스를 조회한다. 필터가 없으면 제목이나
저자에 키워드가 포함된 도서를 검색하고, 필터가 있으면 추가 조건을
적용한다. 검색 결과를 정렬 기준(최신순, 가격순 등)에 따라 정렬한 후
사용자에게 반환한다.

4.7 도서 상세 조회

<img src="./images/media/image16.png"
style="width:5.90556in;height:2.98931in" />

사용자가 특정 도서의 상세 정보를 조회한다. BookService가 도서 정보를
조회하고, 판매자 정보(닉네임, 평점, VIP 상태, 거래 횟수)를 함께
가져온다. 도서의 이미지 목록도 조회하여 사용자에게 도서의 모든 상세
정보를 제공한다.

4.8 찜하기

<img src="./images/media/image17.png"
style="width:5.90556in;height:3.12667in" />

4.9 거래신청

<img src="./images/media/image18.png"
style="width:5.90556in;height:2.88792in" />

4.10 실시간 채팅

<img src="./images/media/image19.png"
style="width:5.90556in;height:3.50611in" />

4.11 결제하기

<img src="./images/media/image20.png"
style="width:5.90556in;height:3.26611in" />

구매자가 거래에 대해 결제를 진행한다. 시스템은 거래 정보를 조회하고 결제
금액을 검증한다. 활성 상태인 관리자 계좌 정보를 가져와서 구매자에게 입금
정보를 안내한다. 구매자가 관리자 계좌로 입금한 후 입금 완료를 확인하면,
결제 상태를 '완료'로 변경하고 거래 상태를 '결제 완료'로 업데이트한다. 이
3자 결제 시스템을 통해 거래의 안전성을 확보한다.

4.12 거래완료

<img src="./images/media/image21.png"
style="width:5.90556in;height:2.82333in" />

구매자가 도서를 전달받고 거래 완료를 확인한다. 구매자 본인이고 결제가
완료된 상태인지 검증한 후, 거래 상태를 '완료'로 변경하고 도서 상태를
'판매 완료'로 업데이트한다. 판매자에게 거래 완료 알림을 전송하고,
구매자에게 후기 작성을 안내한다.

4.13후기 작성

<img src="./images/media/image22.png"
style="width:5.90556in;height:3.83819in" />

구매자가 거래 완료 후 판매자에 대한 후기를 작성한다. 평점(1-5점)과
내용(최대 500자)을 입력받아 유효성을 검증한다. 이미 작성한 후기가 있는지
확인하고, 중복이 아닌 경우 후기를 저장한다. 판매자의 평균 평점과 후기
개수를 업데이트하고, VIP 등급 조건(거래 10회 이상 + 평점 4.5점 이상)을
만족하는지 확인하여 VIP 상태를 부여한다.

4.14 거래상황조회

<img src="./images/media/image23.png"
style="width:5.90556in;height:3.92125in" />

사용자가 자신이 참여한 모든 거래 내역을 조회한다. 구매자 또는 판매자로
참여한 거래를 모두 가져와서 도서 정보와 상대방 닉네임을 함께 조회한다.
거래 상태별로 그룹화하여 사용자에게 제공하며, 최신 순으로 정렬된다.

4.15 관리자 로그인

<img src="./images/media/image24.png"
style="width:5.90556in;height:3.34917in" />

4.16관리자 추가

<img src="./images/media/image25.png"
style="width:5.90556in;height:3.34in" />

4.17회원 목록 조회

<img src="./images/media/image26.png"
style="width:5.90556in;height:2.70333in" />

4.18 신고처리

<img src="./images/media/image27.png"
style="width:5.90556in;height:5.21292in" />

관리자가 사용자 신고를 처리한다. 먼저 처리 대기 중인 신고 목록을
조회한다. 관리자가 특정 신고에 대해 승인 또는 기각을 결정하고 사유를
입력한다. 신고가 승인되면 신고된 사용자에게 경고를 추가하고, 경고 횟수가
3회 이상이면 자동으로 강퇴 처리된다. 신고가 기각되면 신고 상태만
업데이트한다.

4.19 강퇴처리

<img src="./images/media/image28.png"
style="width:5.90556in;height:3.57986in" />

4.20 대금결제

<img src="./images/media/image29.png"
style="width:5.90556in;height:4.87153in" />

4.21관리자 로그아웃

<img src="./images/media/image30.png"
style="width:5.90556in;height:2.42653in" />
