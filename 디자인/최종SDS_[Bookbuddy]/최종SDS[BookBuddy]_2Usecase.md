2\. Use case analysis

<img src="./images/media/image2.png"
style="width:6.39583in;height:6.92708in" />

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #1.1 : 회원가입 (Sign Up)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 학교 이메일 인증을 통해 BookBuddy 플랫폼에 가입한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Guest (비로그인 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td><p>사용자가 회원가입 페이지에 접근할 수 있어야 한다. 학교 이메일
도메인</p>
<p><u>(<a href="mailto:@ynu.ac.kr">@ynu.ac.kr</a>)이 시스템에
등록되어</u> 있어야 한다.</p></td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 회원가입 페이지에서 학교 이메일을 입력하고 인증을 시작할
때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>새로운 사용자 계정이 시스템에 생성된다. 사용자는 로그인 페이지로
이동한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>사용자 계정이 생성되지 않는다. 사용자는 회원가입 페이지에
남아있다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>Guest가 회원가입을 한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 Guest가 회원가입 페이지로 이동할 때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 이메일 입력 폼을 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>Guest가 학교 이메일 주소를 입력한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 입력된 이메일이 학교 도메인(<a
href="mailto:@ynu.ac.kr">@ynu.ac.kr</a>)인지 검증한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 6자리 인증 코드를 생성하여 입력된 이메일로 발송한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 인증 코드 입력 폼을 표시한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>Guest가 받은 인증 코드를 입력한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 인증 코드가 일치하는지 확인한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 회원 정보 입력 폼(아이디, 비밀번호, 학과, 학번)을
표시한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>Guest가 모든 필수 정보를 입력한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 아이디 형식(4-20자 영문, 숫자 조합)을 검증한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>시스템은 비밀번호 형식(8-20자 영문, 숫자, 특수문자 조합)을
검증한다.</td>
</tr>
<tr>
<td><strong>13</strong></td>
<td>시스템은 아이디 중복 여부를 확인한다.</td>
</tr>
<tr>
<td><strong>14</strong></td>
<td>시스템은 모든 필수 항목이 입력되었는지 확인한다.</td>
</tr>
<tr>
<td><strong>15</strong></td>
<td>시스템은 새로운 사용자 계정을 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>16</strong></td>
<td>시스템은 "회원가입이 완료되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>17</strong></td>
<td>시스템은 로그인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>18</strong></td>
<td>이 Use case는 회원가입이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td>4</td>
<td>4a. 학교 이메일이 아닌 경우<br />
...4a1. 시스템은 "학교 이메일을 입력해주세요 (<a
href="mailto:@ynu.ac.kr">@ynu.ac.kr</a>)" 에러 메시지를 표시한다.<br />
...4a2. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td>8</td>
<td>8a. 인증 코드가 일치하지 않는 경우<br />
...8a1. 시스템은 "인증 코드가 일치하지 않습니다" 에러 메시지를
표시한다.<br />
...8a2. Use case는 step 7로 돌아간다.</td>
</tr>
<tr>
<td>11</td>
<td>11a. 아이디 형식이 올바르지 않은 경우<br />
...11a1. 시스템은 "아이디는 4-20자의 영문, 숫자 조합이어야 합니다" 에러
메시지를 표시한다.<br />
...11a2. Use case는 step 10으로 돌아간다.</td>
</tr>
<tr>
<td>12</td>
<td>12a. 비밀번호 형식이 올바르지 않은 경우<br />
...12a1. 시스템은 "비밀번호는 8-20자의 영문, 숫자, 특수문자 조합이어야
합니다" 에러 메시지를 표시한다.<br />
...12a2. Use case는 step 10으로 돌아간다.</td>
</tr>
<tr>
<td>13</td>
<td>13a. 아이디가 중복된 경우<br />
...13a1. 시스템은 "이미 사용 중인 아이디입니다" 에러 메시지를
표시한다.<br />
...13a2. Use case는 step 10으로 돌아간다.</td>
</tr>
<tr>
<td>14</td>
<td>14a. 필수 항목이 누락된 경우<br />
...14a1. 시스템은 누락된 항목을 빨간색으로 표시한다.<br />
...14a2. 시스템은 "필수 항목을 모두 입력해주세요" 메시지를
표시한다.<br />
...14a3. Use case는 step 10으로 돌아간다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 5 seconds (이메일 발송 포함)</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>신규 사용자 가입 시 (예상: 하루 10-20회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #1.2 : 로그인 (Login)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>등록된 사용자가 아이디와 비밀번호를 입력하여 시스템에 접속한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Guest (비로그인 사용자), Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 이미 회원가입을 완료한 상태여야 한다. 계정이 잠금 상태가
아니어야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 로그인 페이지에서 아이디와 비밀번호를 입력하고 로그인
버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>사용자의 세션이 생성된다. 사용자는 메인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>사용자 세션이 생성되지 않는다. 사용자는 로그인 페이지에
남아있다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>Guest가 로그인을 한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 Guest가 로그인 페이지로 이동할 때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 아이디와 비밀번호 입력 폼을 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>Guest가 아이디를 입력한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>Guest가 비밀번호를 입력한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>Guest가 로그인 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 입력된 아이디가 데이터베이스에 존재하는지 확인한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 입력된 비밀번호가 저장된 비밀번호와 일치하는지
확인한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 로그인 실패 횟수를 0으로 초기화한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 사용자 세션을 생성한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 메인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>이 Use case는 로그인이 성공하면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>6a. 아이디가 존재하지 않는 경우<br />
...6a1. 시스템은 로그인 실패 횟수를 1 증가시킨다.<br />
...6a2. 시스템은 "아이디 또는 비밀번호가 일치하지 않습니다" 에러
메시지를 표시한다.<br />
...6a3. 시스템은 입력 필드를 유지한다.<br />
...6a4. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7a. 비밀번호가 일치하지 않는 경우<br />
...7a1. 시스템은 로그인 실패 횟수를 1 증가시킨다.<br />
...7a2. 시스템은 "아이디 또는 비밀번호가 일치하지 않습니다" 에러
메시지를 표시한다.<br />
...7a3. 시스템은 입력 필드를 유지한다.<br />
...7a4. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7b. 로그인 실패 횟수가 5회에 도달한 경우<br />
...7b1. 시스템은 해당 계정을 10분간 잠금 처리한다.<br />
...7b2. 시스템은 잠금 해제 시간을 기록한다.<br />
...7b3. 시스템은 "로그인 시도 횟수 초과. 10분 후 다시 시도해주세요"
메시지를 표시한다.<br />
...7b4. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7c. 계정이 잠금 상태인 경우<br />
...7c1. 시스템은 잠금 해제 시간을 확인한다.<br />
...7c2. 시스템은 "로그인 시도 횟수 초과. X분 후 다시 시도해주세요"
메시지를 표시한다.<br />
...7c3. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>사용자 접속 시 (예상: 하루 100-200회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #1.3 : 로그아웃 (Logout)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 시스템에서 로그아웃하여 세션을 종료한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자), Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 로그아웃 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>사용자의 세션이 종료된다. 로그인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>없음</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 로그아웃을 한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 로그아웃 버튼을 클릭할 때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 현재 사용자의 세션을 종료한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 세션 데이터를 삭제한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 로그인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 "로그아웃되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>이 Use case는 로그아웃이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 1 second</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>사용자 종료 시 (예상: 하루 100-200회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #2.1 : 도서 등록 (Register
Book)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>판매자가 판매하고자 하는 중고 전공책을 시스템에 등록한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 도서 등록 페이지에서 도서 정보를 입력하고 등록 버튼을
클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>새로운 도서가 시스템에 등록된다. 도서가 검색 가능한 상태가 된다.
사용자의 판매 목록에 도서가 추가된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>도서가 등록되지 않는다. 사용자는 도서 등록 페이지에 남아있다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 도서를 등록한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 도서 등록 페이지로 이동할 때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 도서 정보 입력 폼을 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>User가 도서명을 입력한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>User가 저자를 입력한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>User가 출판사를 입력한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>User가 판매 가격을 입력한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>User가 카테고리(학과)를 선택한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>User가 도서 상태 등급(최상/상/중/하)을 선택한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>User가 도서 설명을 입력한다. (선택사항)</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>User가 도서 이미지를 업로드한다. (선택사항)</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 필수 항목(도서명, 저자, 가격, 상태 등급)이 모두
입력되었는지 확인한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>시스템은 등록 버튼을 활성화한다.</td>
</tr>
<tr>
<td><strong>13</strong></td>
<td>User가 등록 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>14</strong></td>
<td>시스템은 도서 정보를 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>15</strong></td>
<td>시스템은 도서 상태를 "판매중"으로 설정한다.</td>
</tr>
<tr>
<td><strong>16</strong></td>
<td>시스템은 등록일을 현재 시간으로 기록한다.</td>
</tr>
<tr>
<td><strong>17</strong></td>
<td>시스템은 "도서가 등록되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>18</strong></td>
<td>시스템은 내 판매 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>19</strong></td>
<td>이 Use case는 도서 등록이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>11a. 필수 항목이 누락된 경우<br />
...11a1. 시스템은 등록 버튼을 비활성화 상태로 유지한다.<br />
...11a2. 시스템은 누락된 항목을 강조 표시한다.<br />
...11a3. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>10a. 이미지 파일 형식이 올바르지 않은 경우<br />
...10a1. 시스템은 "JPG, PNG 형식의 이미지만 업로드 가능합니다" 메시지를
표시한다.<br />
...10a2. Use case는 step 10으로 돌아간다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>10b. 이미지 파일 크기가 제한을 초과한 경우<br />
10b1. 시스템은 "이미지는 5MB 이하만 업로드 가능합니다" 메시지를
표시한다.<br />
10b2. Use case는 step 10으로 돌아간다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 3 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>도서 판매 등록 시 (예상: 하루 20-30회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #2.2 : 도서 검색 (Search
Book)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 키워드, 카테고리, 가격 범위 등으로 원하는 도서를
검색한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Guest (비로그인 사용자), User (로그인한 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>시스템에 등록된 도서가 존재해야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 검색창에 키워드를 입력하고 검색 버튼을 클릭하거나 Enter
키를 누를 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>검색 조건에 맞는 도서 목록이 표시된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>검색 결과가 표시되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>사용자가 도서를 검색한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 사용자가 메인 페이지 또는 검색 페이지로 이동할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 검색창과 필터 옵션을 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>사용자가 검색창에 키워드를 입력한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>사용자가 검색 버튼을 클릭하거나 Enter 키를 누른다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 도서명, 저자, 출판사를 기준으로 키워드를 포함하는 도서를
검색한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 "판매중" 상태의 도서만 필터링한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 검색 결과를 등록일 최신순으로 정렬한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 검색 결과를 페이지당 20개씩 표시한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 검색 결과 개수를 표시한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>사용자는 검색 결과에서 원하는 도서를 선택할 수 있다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>이 Use case는 검색 결과가 표시되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>5a. 검색 결과가 없는 경우<br />
5a1. 시스템은 "검색 결과가 없습니다" 메시지를 표시한다.<br />
5a2. 시스템은 "다른 키워드로 검색해보세요" 안내 메시지를 표시한다. 5a3.
Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>3a. 사용자가 학과 카테고리 필터를 선택하는 경우<br />
3a1. 사용자가 학과를 선택한다.<br />
3a2. 시스템은 선택한 학과의 도서만 필터링한다.<br />
3a3. Use case는 step 6으로 이어진다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td><p>3b. 사용자가 가격 범위 필터를 설정하는 경우<br />
3b1. 사용자가 최소 가격과 최대 가격을 입력한다.<br />
3b2. 시스템은 해당 가격 범위 내의 도서만 필터링한다.</p>
<p>3b3. Use case는 step 6으로 이어진다.</p></td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>3c. 사용자가 상태 등급 필터를 선택하는 경우<br />
3c1. 사용자가 상태 등급(최상/상/중/하)을 선택한다.<br />
3c2. 시스템은 선택한 상태 등급의 도서만 필터링한다.<br />
3c3. Use case는 step 6으로 이어진다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>8a. 검색 결과가 20개를 초과하는 경우<br />
8a1. 시스템은 페이지네이션을 표시한다.<br />
8a2. 사용자는 다음 페이지로 이동할 수 있다.<br />
8a3. Use case는 step 8로 돌아간다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 1 second</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>도서 검색 시 (예상: 하루 200-300회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #2.3 : 도서 조회 (View Book
Details)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 특정 도서의 상세 정보를 조회한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Guest (비로그인 사용자), User (로그인한 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>조회하려는 도서가 시스템에 존재해야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 검색 결과 또는 도서 목록에서 도서를 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>도서의 상세 정보가 표시된다. 도서 조회수가 1 증가한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>도서 정보가 표시되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>사용자가 도서 상세 정보를 조회한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 사용자가 검색 결과 또는 도서 목록에서 도서를 클릭할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 도서 상세 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 도서명을 표시한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 저자를 표시한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 출판사를 표시한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 판매 가격을 표시한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 도서 상태 등급을 표시한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 도서 설명을 표시한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 등록일을 표시한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 등록된 도서 이미지들을 슬라이드 형태로 표시한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 판매자 정보(닉네임, 학과)를 표시한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>시스템은 판매자의 평점과 거래 횟수를 표시한다.</td>
</tr>
<tr>
<td><strong>13</strong></td>
<td>시스템은 도서 조회수를 1 증가시킨다.</td>
</tr>
<tr>
<td><strong>14</strong></td>
<td>시스템은 찜하기, 거래 신청, 판매자에게 문의하기 버튼을
표시한다.</td>
</tr>
<tr>
<td><strong>15</strong></td>
<td>이 Use case는 도서 정보가 표시되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1a. 도서가 존재하지 않는 경우<br />
...1a1. 시스템은 "존재하지 않는 도서입니다" 메시지를 표시한다.<br />
...1a2. 시스템은 이전 페이지로 이동한다.<br />
...1a3. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1b. 도서가 "판매 완료" 상태인 경우<br />
...1b1. 시스템은 "판매 완료" 배지를 표시한다.<br />
...1b2. 시스템은 거래 신청 버튼을 비활성화한다.<br />
...1b3. Use case는 step 3으로 이어진다.</td>
</tr>
<tr>
<td><strong>14</strong></td>
<td>14a. 사용자가 로그인하지 않은 경우<br />
...14a1. 시스템은 찜하기, 거래 신청, 문의하기 버튼을 비활성화한다.<br />
...14a2. 버튼 위에 "로그인이 필요합니다" 툴팁을 표시한다.<br />
...14a3. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>14</strong></td>
<td>14b. 사용자가 판매자 본인인 경우<br />
...14b1. 시스템은 찜하기, 거래 신청 버튼을 숨긴다.<br />
...14b2. 시스템은 "수정", "삭제" 버튼을 표시한다.<br />
...14b3. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>도서 조회 시 (예상: 하루 300-500회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.1 : 찜하기 (Add to
Wishlist)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 관심 있는 도서를 찜 목록에 추가하거나 제거한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다. 도서 상세 페이지에 있어야
한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 도서 상세 페이지에서 찜하기 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>도서가 사용자의 찜 목록에 추가되거나 제거된다. 찜하기 버튼의 상태가
변경된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>찜 목록이 변경되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 도서를 찜한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 도서 상세 페이지에서 찜하기 버튼을 클릭할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 현재 사용자가 해당 도서를 이미 찜했는지 확인한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 찜 정보를 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 찜하기 버튼을 "찜 취소" 상태로 변경한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 버튼 아이콘을 채워진 하트로 변경한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 "찜 목록에 추가되었습니다" 토스트 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>이 Use case는 찜하기가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>2a. 이미 찜한 도서인 경우<br />
...2a1. 시스템은 찜 정보를 데이터베이스에서 삭제한다.<br />
...2a2. 시스템은 찜하기 버튼을 "찜하기" 상태로 변경한다.<br />
...2a3. 시스템은 버튼 아이콘을 빈 하트로 변경한다.<br />
...2a4. 시스템은 "찜 목록에서 제거되었습니다" 토스트 메시지를
표시한다.<br />
...2a5. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1a. 사용자가 로그인하지 않은 경우<br />
...1a1. 시스템은 "로그인이 필요한 서비스입니다" 메시지를 표시한다.<br />
...1a2. 시스템은 로그인 페이지로 이동한다.<br />
...1a3. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1b. 자신이 등록한 도서인 경우<br />
...1b1. 시스템은 "본인이 등록한 도서는 찜할 수 없습니다" 메시지를
표시한다.<br />
...1b2. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 1 second</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>찜하기 사용 시 (예상: 하루 50-100회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.2 : 거래 신청 (Request
Transaction)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>구매자가 판매자에게 도서 구매를 위한 거래를 신청한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자, 구매자 역할)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다. 도서가 "판매중" 상태여야 한다.
자신이 등록한 도서가 아니어야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 도서 상세 페이지에서 "거래 신청" 버튼을 클릭하고 확인할
때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>거래 신청이 데이터베이스에 기록된다. 판매자에게 알림이 전송된다.
도서 상태가 "거래 신청 대기중"으로 표시된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>거래 신청이 기록되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 거래를 신청한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 도서 상세 페이지에서 "거래 신청" 버튼을 클릭할
때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 거래 신청 확인 대화상자를 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>User가 "확인" 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 거래 신청 정보(구매자 ID, 판매자 ID, 도서 ID, 신청 시간)를
생성한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 거래 상태를 "신청 대기"로 설정한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 거래 신청을 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 판매자에게 "새로운 거래 신청이 있습니다" 알림을
전송한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 "거래 신청이 완료되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 거래 신청 버튼을 "거래 신청 대기중"으로 변경한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 거래 상황 조회 페이지로 이동 옵션을 제공한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>이 Use case는 거래 신청이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1a. 사용자가 로그인하지 않은 경우<br />
...1a1. 시스템은 "로그인이 필요한 서비스입니다" 메시지를 표시한다.<br />
...1a2. 시스템은 로그인 페이지로 이동한다.<br />
...1a3. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1b. 자신이 등록한 도서인 경우<br />
...1b1. 시스템은 "본인이 등록한 도서는 구매할 수 없습니다" 메시지를
표시한다.<br />
...1b2. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1c. 도서가 "판매 완료" 상태인 경우<br />
...1c1. 시스템은 "이미 판매 완료된 도서입니다" 메시지를 표시한다.<br />
...1c2. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1d. 이미 거래 신청한 도서인 경우<br />
...1d1. 시스템은 "이미 거래 신청한 도서입니다" 메시지를 표시한다.<br />
...1d2. 시스템은 거래 상황 조회 페이지로 이동 옵션을 제공한다.<br />
...1d3. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>3a. User가 "취소" 버튼을 클릭하는 경우<br />
...3a1. 시스템은 대화상자를 닫는다.<br />
...3a2. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>거래 신청 시 (예상: 하루 30-50회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.3 : 거래 상황 조회 (View Transaction
Status)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>사용자가 진행 중인 거래 상황을 확인한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 마이페이지에서 "거래 상황" 메뉴를 선택할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>거래 목록과 상태 정보가 표시된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>없음</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 거래 상황을 조회한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 마이페이지로 이동할 때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 마이페이지 메뉴를 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>User가 "거래 상황" 메뉴를 선택한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 거래 목록을 표시한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 구매 목록과 판매 목록을 탭으로 구분하여 표시한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 각 거래의 도서명, 상대방 닉네임, 거래 상태, 신청일을
표시한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 거래 상태(신청 대기, 거래 진행중, 거래 완료)를 색상으로
구분하여 표시한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>User는 특정 거래를 클릭하여 상세 정보를 조회할 수 있다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>이 Use case는 거래 목록이 표시되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>4a. 진행 중인 거래가 없는 경우<br />
...4a1. 시스템은 "진행 중인 거래가 없습니다" 메시지를 표시한다.<br />
...4a2. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>8a. 거래 상세 정보를 조회하는 경우<br />
...8a1. 시스템은 거래 상세 페이지로 이동한다.<br />
...8a2. 시스템은 도서 정보, 상대방 정보, 거래 상태, 신청일, 진행 단계를
표시한다.<br />
...8a3. 시스템은 판매자인 경우 "수락", "거절" 버튼을 표시한다.<br />
...8a4. 시스템은 거래 진행중인 경우 채팅 버튼을 표시한다.<br />
...8a5. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>거래 상황 확인 시 (예상: 하루 50-100회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.4 : 결제하기 (Make
Payment)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>구매자가 판매자의 도서를 결제한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자, 구매자 역할)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다. 거래 상태가 "거래 진행중"이어야
한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 거래 상세 페이지에서 "결제하기" 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>결제 정보가 기록된다. 관리자에게 결제 확인 요청이 전송된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>결제 정보가 기록되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 결제를 한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 거래 상세 페이지에서 "결제하기" 버튼을 클릭할
때 시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 결제 안내 페이지를 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 관리자 계좌번호를 표시한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 도서 가격을 표시한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 입금자명 입력 필드를 표시한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>User가 입금자명을 입력한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>User가 관리자 계좌로 송금한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>User가 "결제완료" 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 결제 정보를 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 거래 상태를 "결제완료"로 변경한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 관리자에게 결제 확인 요청 알림을 전송한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>시스템은 "결제가 완료되었습니다. 관리자 확인 후 판매자에게
입금됩니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>13</strong></td>
<td>이 Use case는 결제가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>6a. 입금자명을 입력하지 않은 경우<br />
...6a1. 시스템은 "결제완료" 버튼을 비활성화한다.<br />
...6a2. Use case는 step 6으로 돌아간다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>결제 시 (예상: 하루 20-30회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.5 : 거래 완료 (Complete
Transaction)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>판매자가 거래를 완료 처리한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자, 판매자 역할)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다. 거래 상태가 "거래 진행중" 또는
"결제완료"여야 한다. 사용자가 판매자여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 거래 상세 페이지에서 "거래 완료" 버튼을 클릭하고 확인할
때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>거래 상태가 "거래 완료"로 변경된다. 도서 상태가 "판매 완료"로
변경된다. 구매자에게 알림이 전송된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>거래 상태가 변경되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td>S</td>
<td>User가 거래를 완료한다.</td>
</tr>
<tr>
<td>1</td>
<td>이 Use case는 User가 거래 상세 페이지에서 "거래 완료" 버튼을 클릭할
때 시작된다.</td>
</tr>
<tr>
<td>2</td>
<td>시스템은 거래 완료 확인 대화상자를 표시한다.</td>
</tr>
<tr>
<td>3</td>
<td>User가 "확인" 버튼을 클릭한다.</td>
</tr>
<tr>
<td>4</td>
<td>시스템은 거래 상태를 "거래 완료"로 변경한다.</td>
</tr>
<tr>
<td>5</td>
<td>시스템은 도서 상태를 "판매 완료"로 변경한다.</td>
</tr>
<tr>
<td>6</td>
<td>시스템은 거래 완료 시간을 기록한다.</td>
</tr>
<tr>
<td>7</td>
<td>시스템은 구매자에게 "거래가 완료되었습니다" 알림을 전송한다.</td>
</tr>
<tr>
<td>8</td>
<td>시스템은 "거래가 완료되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td>9</td>
<td>시스템은 거래 완료 페이지로 이동한다.</td>
</tr>
<tr>
<td>10</td>
<td>이 Use case는 거래 완료가 처리되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td>1</td>
<td>1a. 사용자가 구매자인 경우<br />
...1a1. 시스템은 "판매자만 거래 완료 처리를 할 수 있습니다" 메시지를
표시한다.<br />
...1a2. Use case가 종료된다.</td>
</tr>
<tr>
<td>3</td>
<td>3a. User가 "취소" 버튼을 클릭하는 경우<br />
...3a1. 시스템은 대화상자를 닫는다.<br />
...3a2. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 1 second</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>거래 완료 시 (예상: 하루 20-30회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #3.6 : 후기 작성 (Write
Review)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>구매자가 거래 완료 후 판매자에 대한 후기를 작성한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>User level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>User (로그인한 사용자, 구매자 역할)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>사용자가 로그인된 상태여야 한다. 거래 상태가 "거래 완료"여야 한다.
거래 완료 후 30일 이내여야 한다. 해당 거래에 대한 후기를 작성하지
않았어야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>사용자가 거래 완료 목록에서 "후기 작성" 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>후기가 데이터베이스에 저장된다. 판매자의 평점이 업데이트된다. 후기가
판매자 프로필에 표시된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>후기가 저장되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>User가 후기를 작성한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 User가 거래 완료 목록에서 "후기 작성" 버튼을 클릭할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 후기 작성 페이지를 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 별점 선택 UI(1-5점)를 표시한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>시스템은 한 줄 평가 입력 필드(최대 100자)를 표시한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>User가 별점을 선택한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>User가 한 줄 평가를 입력한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>User가 "작성 완료" 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 후기 정보를 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 판매자의 평점을 재계산하여 업데이트한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 "후기가 등록되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 거래 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>이 Use case는 후기 작성이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1a. 거래 완료 후 30일이 경과한 경우<br />
...1a1. 시스템은 "후기 작성 기간이 만료되었습니다" 메시지를
표시한다.<br />
...1a2. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>1b. 이미 후기를 작성한 경우<br />
...1b1. 시스템은 "이미 후기를 작성한 거래입니다" 메시지를
표시한다.<br />
...1b2. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>5a. 별점을 선택하지 않은 경우<br />
...5a1. 시스템은 "작성 완료" 버튼을 비활성화한다.<br />
...5a2. Use case는 step 5로 돌아간다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>6a. 한 줄 평가가 100자를 초과하는 경우<br />
...6a1. 시스템은 "최대 100자까지 입력 가능합니다" 메시지를
표시한다.<br />
...6a2. 시스템은 100자 이후 입력을 차단한다.<br />
...6a3. Use case는 step 6으로 돌아간다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>후기 작성 시 (예상: 하루 15-25회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.1 : 관리자 로그인 (Admin
Login</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 시스템에 접속한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자 계정이 시스템에 등록되어 있어야 한다. 계정이 잠금 상태가
아니어야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 관리자 로그인 페이지에서 아이디와 비밀번호를 입력하고
로그인 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>관리자 세션이 생성된다. 관리자 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>관리자 세션이 생성되지 않는다. 관리자는 로그인 페이지에
남아있다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>Admin이 로그인을 한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 Admin이 관리자 로그인 페이지로 이동할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 아이디와 비밀번호 입력 폼을 표시한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>Admin이 아이디를 입력한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>Admin이 비밀번호를 입력한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>Admin이 로그인 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>시스템은 입력된 아이디가 관리자 계정인지 확인한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>시스템은 입력된 비밀번호가 저장된 비밀번호와 일치하는지
확인한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 로그인 실패 횟수를 0으로 초기화한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 관리자 세션을 생성한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 관리자 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 거래 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>이 Use case는 후기 작성이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>6a. 아이디가 존재하지 않거나 관리자 계정이 아닌 경우<br />
...6a1. 시스템은 로그인 실패 횟수를 1 증가시킨다.<br />
...6a2. 시스템은 "아이디 또는 비밀번호가 일치하지 않습니다" 에러
메시지를 표시한다.<br />
...6a3. 시스템은 입력 필드를 유지한다.<br />
...6a4. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7a. 비밀번호가 일치하지 않는 경우<br />
...7a1. 시스템은 로그인 실패 횟수를 1 증가시킨다.<br />
...7a2. 시스템은 "아이디 또는 비밀번호가 일치하지 않습니다" 에러
메시지를 표시한다.<br />
...7a3. 시스템은 입력 필드를 유지한다.<br />
...7a4. Use case는 step 3으로 돌아간다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7b. 로그인 실패 횟수가 5회에 도달한 경우<br />
...7b1. 시스템은 해당 계정을 10분간 잠금 처리한다.<br />
...7b2. 시스템은 잠금 해제 시간을 기록한다.<br />
...7b3. 시스템은 "로그인 시도 횟수 초과. 10분 후 다시 시도해주세요"
메시지를 표시한다.<br />
...7b4. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7c. 계정이 잠금 상태인 경우<br />
...7c1. 시스템은 잠금 해제 시간을 확인한다.<br />
...7c2. 시스템은 "로그인 시도 횟수 초과. X분 후 다시 시도해주세요"
메시지를 표시한다.<br />
...7c3. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>관리자 접속 시 (예상: 하루 5-10회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.2 : 관리자 추가 (Add
Admin)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 새로운 관리자 계정을 추가한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td>김민형</td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 관리자 페이지에서 "관리자 추가" 메뉴를 선택하고 정보를
입력할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>새로운 관리자 계정이 생성된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>관리자 계정이 생성되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td>S</td>
<td>Admin이 새로운 관리자를 추가한다.</td>
</tr>
<tr>
<td>1</td>
<td>이 Use case는 Admin이 관리자 페이지에서 "관리자 추가" 메뉴를 선택할
때 시작된다.</td>
</tr>
<tr>
<td>2</td>
<td>시스템은 관리자 정보 입력 폼을 표시한다.</td>
</tr>
<tr>
<td>3</td>
<td>Admin이 새 관리자의 아이디를 입력한다.</td>
</tr>
<tr>
<td>4</td>
<td>Admin이 새 관리자의 비밀번호를 입력한다.</td>
</tr>
<tr>
<td>5</td>
<td>Admin이 비밀번호 확인을 입력한다.</td>
</tr>
<tr>
<td>6</td>
<td>시스템은 아이디 형식(4-20자 영문, 숫자 조합)을 검증한다.</td>
</tr>
<tr>
<td>7</td>
<td>시스템은 비밀번호 형식(8-20자 영문, 숫자, 특수문자 조합)을
검증한다.</td>
</tr>
<tr>
<td>8</td>
<td>시스템은 비밀번호와 비밀번호 확인이 일치하는지 확인한다.</td>
</tr>
<tr>
<td>9</td>
<td>시스템은 아이디 중복 여부를 확인한다.</td>
</tr>
<tr>
<td>10</td>
<td>시스템은 모든 필수 항목이 입력되었는지 확인한다.</td>
</tr>
<tr>
<td>11</td>
<td>Admin이 "추가" 버튼을 클릭한다.</td>
</tr>
<tr>
<td>12</td>
<td>시스템은 새로운 관리자 계정을 데이터베이스에 저장한다.</td>
</tr>
<tr>
<td>13</td>
<td>시스템은 "관리자가 추가되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td>14</td>
<td>시스템은 관리자 페이지로 이동한다.</td>
</tr>
<tr>
<td>15</td>
<td>이 Use case는 관리자 추가가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td>x</td>
<td></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>새 관리자 추가 시 (예상: 한 달에 1-2회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.3 : 회원 목록 조회 (View User
List)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 전체 회원 정보를 조회한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 관리자 페이지에서 "회원 관리" 메뉴를 선택할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>회원 목록이 표시된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>없음</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td>S</td>
<td>Admin이 회원 목록을 조회한다.</td>
</tr>
<tr>
<td>1</td>
<td>이 Use case는 Admin이 관리자 페이지에서 "회원 관리" 메뉴를 선택할 때
시작된다.</td>
</tr>
<tr>
<td>2</td>
<td>시스템은 전체 회원 목록을 조회한다.</td>
</tr>
<tr>
<td>3</td>
<td>시스템은 회원 목록을 표시한다.</td>
</tr>
<tr>
<td>4</td>
<td>시스템은 각 회원의 아이디, 닉네임, 학과, 가입일, 신고 누적 횟수를
표시한다.</td>
</tr>
<tr>
<td>5</td>
<td>시스템은 회원 목록을 가입일 최신순으로 정렬한다.</td>
</tr>
<tr>
<td>6</td>
<td>시스템은 검색 기능을 제공한다.</td>
</tr>
<tr>
<td>7</td>
<td>Admin은 특정 회원을 클릭하여 상세 정보를 조회할 수 있다.</td>
</tr>
<tr>
<td>8</td>
<td>이 Use case는 회원 목록이 표시되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>6a. Admin이 회원을 검색하는 경우<br />
...6a1. Admin이 검색 키워드를 입력한다.<br />
...6a2. 시스템은 아이디, 닉네임, 학과를 기준으로 검색한다.<br />
...6a3. 시스템은 검색 결과를 표시한다.<br />
...6a4. Use case가 종료된다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7a. 회원 상세 정보를 조회하는 경우<br />
...7a1. 시스템은 회원 상세 페이지로 이동한다.<br />
...7a2. 시스템은 회원의 모든 정보를 표시한다.<br />
...7a3. 시스템은 거래 내역, 신고 내역을 표시한다.<br />
...7a4. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>회원 관리 시 (예상: 하루 5-10회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.4 : 신고 처리 (Handle
Report)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 신고된 게시글이나 사용자를 처리한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다. 처리되지 않은 신고가 존재해야
한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 신고 목록에서 특정 신고를 선택하고 처리할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>신고가 처리된다. 조치 시 대상 사용자의 신고 누적 횟수가
증가한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>신고가 처리되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>Admin이 신고를 처리한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 Admin이 관리자 페이지에서 신고 관리 메뉴를 선택할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 접수된 신고 목록을 확인한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 신고 목록에 신고 대상, 신고 사유, 신고일, 처리 상태를
표시한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>Admin이 처리할 신고를 선택한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>시스템은 신고 상세 정보를 표시한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>Admin이 신고 내용을 검토한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>Admin이 "반려" 또는 "조치" 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 신고 처리 상태를 업데이트한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 "신고가 처리되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 신고 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>이 Use case는 신고 처리가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7a. Admin이 "조치" 버튼을 클릭한 경우<br />
...7a1. 시스템은 해당 사용자의 신고 누적 횟수를 1회 증가시킨다.<br />
...7a2. 시스템은 신고된 게시글을 삭제한다.<br />
...7a3. 시스템은 대상 사용자에게 경고 알림을 전송한다.<br />
...7a4. Use case는 step 8로 이어진다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>7b. Admin이 "반려" 버튼을 클릭한 경우<br />
...7b1. 시스템은 신고 상태를 "반려"로 변경한다.<br />
...7b2. Use case는 step 8로 이어진다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>Branching Action</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>신고 처리 시 (예상: 하루 3-5회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.5 : 강퇴 기능 (Ban
User)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 신고 누적 회원을 강제 탈퇴시킨다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다. 대상 회원의 신고 누적 횟수가 3회
이상이어야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 회원 상세 페이지에서 "강퇴" 버튼을 클릭하고 확인할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>회원이 강제 탈퇴된다. 회원의 모든 게시글이 삭제된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>회원이 강퇴되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td>S</td>
<td>Admin이 회원을 강퇴한다.</td>
</tr>
<tr>
<td>1</td>
<td>이 Use case는 Admin이 회원 상세 페이지에서 "강퇴" 버튼을 클릭할 때
시작된다.</td>
</tr>
<tr>
<td>2</td>
<td>시스템은 신고 누적 횟수가 3회 이상인지 확인한다.</td>
</tr>
<tr>
<td>3</td>
<td>시스템은 강퇴 확인 대화상자를 표시한다.</td>
</tr>
<tr>
<td>4</td>
<td>Admin이 "확인" 버튼을 클릭한다.</td>
</tr>
<tr>
<td>5</td>
<td>시스템은 해당 회원을 강제 탈퇴 처리한다.</td>
</tr>
<tr>
<td>6</td>
<td>시스템은 회원의 세션을 즉시 종료한다.</td>
</tr>
<tr>
<td>7</td>
<td>시스템은 회원의 계정을 비활성화한다.</td>
</tr>
<tr>
<td>8</td>
<td>시스템은 회원의 모든 게시글을 삭제한다.</td>
</tr>
<tr>
<td>9</td>
<td>시스템은 "회원이 강퇴되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td>10</td>
<td>시스템은 회원 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td>11</td>
<td>이 Use case는 강퇴가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Branching Action</strong></td>
</tr>
<tr>
<td>2</td>
<td>2a. 신고 누적 횟수가 3회 미만인 경우<br />
...2a1. 시스템은 "신고 누적 3회 이상인 회원만 강퇴할 수 있습니다"
메시지를 표시한다.<br />
...2a2. Use case가 종료된다.</td>
</tr>
<tr>
<td>4</td>
<td>4a. Admin이 "취소" 버튼을 클릭하는 경우<br />
...4a1. 시스템은 대화상자를 닫는다.<br />
...4a2. Use case가 종료된다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 2 seconds</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>강퇴 처리 시 (예상: 한 달에 1-2회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.6 : 관리자 로그아웃 (Admin
Logout)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자가 시스템에서 로그아웃한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 로그아웃 버튼을 클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>관리자 세션이 종료된다. 로그인 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>없음</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td>S</td>
<td>Admin이 로그아웃을 한다.</td>
</tr>
<tr>
<td>1</td>
<td>이 Use case는 Admin이 로그아웃 버튼을 클릭할 때 시작된다.</td>
</tr>
<tr>
<td>2</td>
<td>시스템은 현재 관리자의 세션을 종료한다.</td>
</tr>
<tr>
<td>3</td>
<td>시스템은 세션 데이터를 삭제한다.</td>
</tr>
<tr>
<td>4</td>
<td>시스템은 로그인 페이지로 이동한다.</td>
</tr>
<tr>
<td>5</td>
<td>시스템은 "로그아웃되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td>6</td>
<td>이 Use case는 로그아웃이 완료되면 끝난다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>시스템은 거래 목록 페이지로 이동한다.</td>
</tr>
<tr>
<td><strong>12</strong></td>
<td>이 Use case는 후기 작성이 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 91%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>EXTENSION SCENARIOS</strong></td>
</tr>
<tr>
<td><strong>x</strong></td>
<td></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 85%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td><strong>Performance</strong></td>
<td>≤ 1 second</td>
</tr>
<tr>
<td><strong>Frequency</strong></td>
<td>관리자 종료 시 (예상: 하루 5-10회)</td>
</tr>
<tr>
<td><strong>Due Date</strong></td>
<td>2025.11.07</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>Use case #4.7 : 대금결제 (Process
Payment)</strong></td>
</tr>
<tr>
<td colspan="2"><strong>GENERAL CHARACTERISTICS</strong></td>
</tr>
<tr>
<td><strong>Summary</strong></td>
<td>관리자 계좌에 입금된 금액을 판매자에게 입금한다.</td>
</tr>
<tr>
<td><strong>Scope</strong></td>
<td>BookBuddy (전공책 중고거래 플랫폼)</td>
</tr>
<tr>
<td><strong>Level</strong></td>
<td>Admin level</td>
</tr>
<tr>
<td><strong>Author</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Last Update</strong></td>
<td>2025.11.05</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Analysis</td>
</tr>
<tr>
<td><strong>Primary Actor</strong></td>
<td>Admin (관리자)</td>
</tr>
<tr>
<td><strong>Preconditions</strong></td>
<td>관리자가 로그인된 상태여야 한다. "결제완료" 상태의 거래가 존재해야
한다.</td>
</tr>
<tr>
<td><strong>Trigger</strong></td>
<td>관리자가 결제 관리 페이지에서 특정 거래를 선택하고 처리완료 버튼을
클릭할 때</td>
</tr>
<tr>
<td><strong>Success Post Condition</strong></td>
<td>판매자에게 대금이 입금된다. 거래 상태가 "처리완료"로 변경된다.</td>
</tr>
<tr>
<td><strong>Failed Post Condition</strong></td>
<td>대금이 입금되지 않는다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<tbody>
<tr>
<td colspan="2"><strong>MAIN SUCCESS SCENARIO</strong></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td><strong>Action</strong></td>
</tr>
<tr>
<td><strong>S</strong></td>
<td>Admin이 대금을 처리한다.</td>
</tr>
<tr>
<td><strong>1</strong></td>
<td>이 Use case는 Admin이 관리자 페이지에서 "결제 관리" 메뉴를 선택할 때
시작된다.</td>
</tr>
<tr>
<td><strong>2</strong></td>
<td>시스템은 "결제완료" 상태의 거래 목록을 조회한다.</td>
</tr>
<tr>
<td><strong>3</strong></td>
<td>시스템은 각 거래의 구매자, 판매자 이름, 도서명, 금액, 판매자
계좌번호를 표시한다.</td>
</tr>
<tr>
<td><strong>4</strong></td>
<td>Admin이 처리할 거래를 선택한다.</td>
</tr>
<tr>
<td><strong>5</strong></td>
<td>Admin이 구매자가 송금했는지 확인한다.</td>
</tr>
<tr>
<td><strong>6</strong></td>
<td>Admin이 판매자 계좌번호를 확인하고 입금된 금액을 송금한다.</td>
</tr>
<tr>
<td><strong>7</strong></td>
<td>Admin이 "처리완료" 버튼을 클릭한다.</td>
</tr>
<tr>
<td><strong>8</strong></td>
<td>시스템은 거래 상태를 "처리완료"로 업데이트한다.</td>
</tr>
<tr>
<td><strong>9</strong></td>
<td>시스템은 "결제가 처리되었습니다" 메시지를 표시한다.</td>
</tr>
<tr>
<td><strong>10</strong></td>
<td>시스템은 "결제완료" 거래 목록을 다시 표시한다.</td>
</tr>
<tr>
<td><strong>11</strong></td>
<td>이 Use case는 대금 처리가 완료되면 끝난다.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 8%" />
<col style="width: 70%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr>
<td colspan="3"><strong>EXTENSION SCENARIOS</strong></td>
<td></td>
</tr>
<tr>
<td><strong>Step</strong></td>
<td colspan="2"><strong>Branching Action</strong></td>
<td></td>
</tr>
<tr>
<td>5</td>
<td colspan="2">5a. 구매자가 송금하지 않은 경우<br />
...5a1. Admin은 구매자에게 연락하여 송금을 요청한다.<br />
...5a2. Use case는 step 4로 돌아간다.</td>
<td></td>
</tr>
<tr>
<td colspan="4"><strong>RELATED INFORMATION</strong></td>
</tr>
<tr>
<td colspan="2"><strong>Performance</strong></td>
<td colspan="2">≤ 2 seconds</td>
</tr>
<tr>
<td colspan="2"><strong>Frequency</strong></td>
<td colspan="2">대금 처리 시 (예상: 하루 20-30회)</td>
</tr>
<tr>
<td colspan="2"><strong>Due Date</strong></td>
<td colspan="2">2025.11.07</td>
</tr>
</tbody>
</table>
