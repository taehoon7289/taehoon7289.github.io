# api 수정요청건

# 2021.02.02
1. 나이스 인증 (휴대폰인증) api 호출후 

https://nice.checkplus.co.kr/CheckPlusSafeModel/checkplus.cb 에서 입력후 

나이스 인증 (휴대폰인증) api 호출시 파라미터 값 rtnUrl 로 돌아오지 않고

https://black-mobile.wizzney.com/Main/Regist 로 이동하고 있는데 확인 요청 드립니다.

2. 아까 https://black-mobile.wizzney.com/Main/Regist 이동할때는 querystring으로 

name, phone, niceSeq 파라미터가 같이 왔는데 추가 가능할까요?

3. 

# 2021.02.04

1. 카카오 sns 회원가입하고 
/api/user/oauth/login 로그인시 
rtnUrl값 페이지로
{"resultCode":"0000","resultMsg":"Success","loginType":"0","snsId":"1617199107","nick":"kakaoappg","authType":"1","enabled":"Y","userLvId":"1"}

받는데 데이터부분에 authorization 값도 같이 포함해서 보내주실수 있나요?

2. 아이디찾기 - 휴대폰 인증번호 전송
/api/user/findId/sendAuthValue 호출시 {"resultCode":"0000","resultMsg":"인증번호 저장 되었습니다."} 라고 리턴오기는 한데
실제 휴대폰인증번호는 오지 않고 있는데 확인 부탁드립니다.

3. authorization 값
/api/user/oauth/login 호출시 rtnUrl 페이지로 이동시 헤더로 넣어주신건가요??
"rtnUrl": "http://106.240.232.36:8081/oauth/success" 로 보내고 있는중인데
http://106.240.232.36:8081/oauth/success 이동할때인가요?

페이지이동하는 형태라 ajax 처럼 response header를 가져오지 못할꺼같은데 데이터 {"resultCode":"0000","resultMsg":"Success","loginType":"0","snsId":"1617199107","nick":"kakaoappg","authType":"1","enabled":"Y","userLvId":"1"} 여기에 포함해서 받을수 있을까요?

authorizePageUri 페이지 로드해서 url이 redirect 되는 형태라 response header 값 접근이 안될꺼라서요

# 2021.02.05

1. /api/user/sendAuthValueByEmail 호출시 
{"resultCode":"0000","resultMsg":"인증번호 저장 되었습니다."} 응답이 오는데
실제로 메일이 안오는데 확인 요청드립니다.

# 2021.02.08
1. 
1:1문의 등록/수정 (/api/customer/myquestion/save) 호출시 500 : Internal Server Error 라는데 확인해주실수 있나요?
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjAzVkp0dUJPIiwiaWF0IjoxNjEyNzQ0Nzg0LCJleHAiOjE2MTI4MzExODR9.rHJR1fOb0slTy1ItGJ8wo-rVMCzA-KPb49TP_hFwuxI

[위즈니 구독]
http://106.240.232.36:8081/
내부 확인용 url 입니다.

그리고 1:1문의등록/수정쪽에 파일 업로드도 있던데 회원가입때처럼 multipart formdata 식으로 ???

# 2021.02.15
1. 파티생성시 ('/api/party/add')에 {"resultCode":"9999","resultMsg":"휴대폰 인증, 계좌 인증을 완료해 주세요."} 리턴오는데 회원가입시 휴대폰인증, 계좌번호 입력했는데도 인증해야되나요? 현재 제 계정 taehoon.kim@appg.co.kr이며, 로그인시  authType: "2" 로 오고 있습니다.

2. 카테고리가져오기(/api/common/categoryList) 데이터로 넷플릭스, 왓차플레이, 웨이브 등 카테고리 보여줄때 url 값이 로고 이미지 url 의미하는건가요??

# 2021.02.16
1. 파티상세페이지 (/api/party/detail) 호출시 500: Internal Server Error 응답오는데 확인가능하실까요? 

Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE1M1pXUlUxIiwiaWF0IjoxNjEzNDQ5MTM5LCJleHAiOjE2MTM1MzU1Mzl9.6-C9na3OFjuNW7_VPRECLlocg55nMNAXxX15p_Hlg6I

parameter:
{
    "partyNo": "72"
}

2. 메인페이지에서 '리뷰' 부분이 '공지'로 변경되었다고 하는데, 메인페이지 api(/api/main/subscribeShare) 호출시 review 데이터 그대로 바인딩 하면 될까요?

3. 파티 상세(/api/party/detail)에서 카테고리 구분값 추가해주실수 있나요? 넷플릭스, 왓챠 등 그리고 로고 이미지는 url로 받는건가요? 아니면 이미지 수급 받나요?

# 2021.02.17
1. 파티 결제 페이지(/api/party/subscribe) api 호출시 {resultCode: "9999", resultMsg: "Fail", partyInfo: null, subscriberInfo: null} 응답오는데 어떤게 문제인지 확인가능할까요?
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE2b1JjUUc2IiwiaWF0IjoxNjEzNTIyMDgxLCJleHAiOjE2MTM2MDg0ODF9.EvNAwxTdfEDzUlLARuL6wym5CrFhnEFEy1L2v9Ub3gI
parameter : {"partyNo":"81","partyAgree":"Y"} 

2. 파티 결제 페이지(/api/party/subscribe) api 호출시 sns 계정임에도 
subscriberInfo: {nick: "카카오앱지", login_type: null, sns_id: null, cash: "0", point: "0"}
login_type 과 sns_id가 null 로 오고 있는데 확인 요청 드립니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE3UEIyM2V3IiwiaWF0IjoxNjEzNTM1MTAyLCJleHAiOjE2MTM2MjE1MDJ9.O3OB2_EDuH7Crpmzhaid_S9yC5Sq-_1SWKg7z019K68

3. 파티 결제시 (/api/cash/settlePayload) api 호출할때 (신용카드,위즈캐시) 두가지 결제방식 모두 /api/cash/settlePayload 호출하는건가요?

4. 위즈피디아 총 개수(/api/wizzpedia/wizzpediaMain) 호출시에 count 값이 39678 인데 리스트(/api/wizzpedia/searchWizzpedia)
검색시 {resultCode: null, resultMsg: null, list: [], count: 0} 응답이 와서 조회 안되는거 확인가능하실까요? 파라미터는
{search: "설국", page: 1, category: "netflix"} 또는 {search: "", page: 1, category: ""} 이외에 다른 카테고리로도 호출해봤습니다.

5. 파티희망게시판 파티생성 관련 api리스트문서나 api규격서 문서에서 안보이는데 어디서 확인가능할까요?

# 2021.02.18

1. api_규격서3 에 2-3 상세페이지 Base Request URL이 2-1.총개수 url로 되어있는데 2-3 상세페이지 Base Request URL 어떻게 되는지 확인요청드립니다.

# 2021.02.19

1. 댓글 수정, 삭제전에 본인글 인지 체크가 필요한데 로그인한 본인체크할수 있는 값을 댓글 리스트(/api/wizzpedia/getCommentList) 추가 필요할꺼같은데 확인 요청드립니다.
{"resultCode":null,"resultMsg":null,"list":[{"seq":93,"id":16511,"category":"wavve","wizzneyId":"WIZZNEY210217PB23ew","name":null,"comment":"5점5점","starRating":5,"wrtime":"2021-02-18 17:46:13","status":"NONE"},{"seq":94,"id":16511,"category":"wavve","wizzneyId":"WIZZNEY2102153ZWRU1","name":"김태훈","comment":"3점짜리","starRating":3,"wrtime":"2021-02-19 09:57:38","status":"NONE"}]}

2. 댓글 수정 api는 api 규약서에 없어서, api 추가 요청 드립니다.

3. 댓글 작성(/api/wizzpedia/writeComment) 최대 500자까지 등록인데 500자로 호출하면 
Data too long for column 'comment' at row 1
에러 발생하여 확인 요청드립니다.

4. sns 계정으로 댓글작성시 name 이 null 로 오고 있음.
{"resultCode":null,"resultMsg":null,"list":[{"seq":93,"id":16511,"category":"wavve","wizzneyId":"WIZZNEY210217PB23ew","name":null,"comment":"5점5점","starRating":5,"wrtime":"2021-02-18 17:46:13","status":"NONE"}]}

5. 파티희망게시판 리스트(/api/party/hopeList) 응답데이터중에 결과 총 개수도 추가 해주실수 있나요? 위즈피디아 리스트(/api/wizzpedia/searchWizzpedia) 과 동일하게 count 추가 요청드립니다.

6. 파티희망게시판 리스트(/api/party/hopeList) 조회시 검색단어, 정렬기준(신규등록순, 짧은기간, 긴기간, 업데이트 순) parameter 도 필요해서 위즈피디아 리스트(/api/wizzpedia/searchWizzpedia) 처럼 search와 sort 추가 요청드립니다.

7. sort에 LONG, SHORT 넣을때 500error 발생하는데 확인가능할까요?

8. 비로그인일경우에도 위즈피디아 검색 및 검색 결과, 파티 희망 게시판 페이지 접근가능이라 authrization 값 없이도 위즈피디아 리스트(/api/wizzpedia/searchWizzpedia), 파티희망게시판 리스트(/api/party/hopeList) 호출가능해야할거같은데 현재 Fail 로 응답이오고 있어서 확인 요청 드립니다.

# 2021.02.22

1. 파티희망게시판 상세(/api/party/partyHopeDetail) 도 비로그인시에 호출 가능하게 요청드립니다.

# 2021.02.23

1. 파티 결제 (카드) ('/api/cash/settlePayload') 호출해서 settleUrl 값으로 세틀뱅크결제 페이지 이동시 오류페이지가 뜨는데 확인 가능할까요?

2. 본인인증이나 sns 로그인때처럼 rtnUrl 값이 필요한데 pnextPUrl, pcancPUrl 값을 프론트에서 변경해서 (ex: http://106.240.232.36:8081/settle/next, http://106.240.232.36:8081/settle/cancel) settleUrl 페이지 호출 해도 결제처리에 문제가 없을지 확인요청드립니다.

3. pnextPUrl = http://106.240.232.36:8081/settle/next, pcancPUrl = http://106.240.232.36:8081/settle/cancel 변경해서 확인했을경우 settlebank 결제 완료후에 세틀뱅크쪽에서 http://106.240.232.36:8081/settle/next 를 호출해줄때 POST 로 호출해서 서버쪽에서 받아야할거같습니다.

4. 개인정보 수정 – 휴대폰 인증번호 전송 (/api/myPage/myUserInfo/sendAuthValue) 호출시 {"resultCode":"0000","resultMsg":"인증번호 저장 되었습니다."} 응답오지만 실제 인증번호는 발송이 안되는거 같은데 확인요청 드립니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE1M1pXUlUxIiwiaWF0IjoxNjE0MDYxNjA2LCJleHAiOjE2MTQxNDgwMDZ9.sa10jZtIEwwWtZfUHb2cbgHz_8gHUem7CyTVvBWa0dc
parameter : {"phone":"01050957289"}

# 2021.02.24

1. 개인정보 확인('/api/myPage/myUserInfo/detail') parameter: {havePwYn: 0, pw: "qwer1234@"} 비밀번호가 일치하는경우이지만, {"resultCode":null,"resultMsg":null,"userInfo":null} 응답오며, 비밀번호가 일치하지 않는경우, {"resultCode":"9999","resultMsg":"Fail","userInfo":null} 로 오고 있어서 확인 요청.

2. 개인정보수정관련하여 본인인증시 ('/api/auth/niceAuthPop') 호출 parameter: {"callType":1,"rtnUrl":"http://106.240.232.36:8081/my-info/success","failRtnUrl":"http://106.240.232.36:8081/my-info/fail"} 로 호출할경우, https://black-payment.wizzney.com/api/auth/niceAuthSuccess로 페이지 이동하고 있음. callType: 0 인 회원가입 경우엔 정상적으로 rtnUrl 로 이동하고 있음.

3. 파티결제완료페이지(/api/cash/paymentResult) 호출시 {"timestamp":1614146815100,"status":500,"error":"Internal Server Error","message":"nested exception is org.apache.ibatis.type.TypeException: Could not set parameters for mapping: ParameterMapping{property='POid', mode=IN, javaType=class java.lang.String, jdbcType=null, numericScale=null, resultMapId='null', jdbcTypeName='null', expression='null'}. Cause: org.apache.ibatis.type.TypeException: Error setting null for parameter #2 with JdbcType OTHER . Try setting a different JdbcType for this parameter or a different jdbcTypeForNull configuration property. Cause: java.sql.SQLException: 부적합한 열 유형: 1111","path":"/api/cash/paymentResult"} 발생하고 있어서 확인요청드립니다.
parameter: {"POid":"WIZZNEY210216oRcQG6-95-20210224150624-100-100","partyNo":"95"}
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE2b1JjUUc2IiwiaWF0IjoxNjE0MTQ1MzQ0LCJleHAiOjE2MTQyMzE3NDR9.FZtz2z9nHIDpG9qFwgEHBTIIz2hCYc0gckEPX7oK3jc

4. 개인정보확인 (/api/myPage/myUserInfo/detail) 응답데이터중에 
1. userInfo 중 profile url로 이미지가 나오지 않고 있음.
profile: "https://black-file.wizzney.com/img/wizzney/20210265_20210224152139.jpg"
2. 개인정보변경('/api/myPage/myUserInfo/update') 한후 로그인(/api/user/login)한후에 profile: null 로 들어오고 있음.

개인정보변경('/api/myPage/myUserInfo/update')으로 변경후에 나온 사항이고, 두가지 확인부탁드립니다.

# 2021.02.26

1. 개인정보변경('/api/myPage/myUserInfo/update') 확인시 응답데이터로 {"resultCode":"0000","resultMsg":"수정 되었습니다."} 로 추가데이터가 포함안되있는데 확인요청드립니다.

2. 개인정보 수정 – 휴대폰 인증번호 전송('/api/myPage/myUserInfo/sendAuthValue') sns계정으로 호출시 {"resultCode":"9999","resultMsg":"인증번호 저장에 실패하였습니다."} 응답오고 있어서 확   인부탁드립니다. 인증번호이전에 본인인증('/api/auth/niceAuthPop') callType: 1 로 본인인증 후에 휴대폰 인증번호 전송('/api/myPage/myUserInfo/sendAuthValue') 한 경우입니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE3UEIyM2V3IiwiaWF0IjoxNjE0MzEyMzE3LCJleHAiOjE2MTQzOTg3MTd9.WN9nsvwtuo_4-cEF9a2nPaj76cthIPyP6sY903WeggI

3. 회원탈퇴부분 확인하려는데 jungmin.nam@appg.co.kr 계정에 포인트 없애주실수 있나요? 회원탈퇴체크('/api/myPage/myUserInfo/withdrawal/check') 에서 {"resultCode":"9999","resultMsg":"사용 가능한 캐시가 있습니다."} 응답오고 있어서 요청드립니다.

4. 개인정보변경('/api/myPage/myUserInfo/update') 수정하여 info 데이터중 authType: 4 로 받는거 확인했었는데, 해당계정으로 로그아웃/재로그인시 authType: 2 또는 1 로 오고 있어서 로그인시 data 확인 부탁드립니다. taehoon.kim@appg.co.kr 계정 authType: 2로 오고 있으며, 카카오 sns 계정은 authType: 1로 오고 있습니다.


5. 생성한 파티 리스트 (/api/myPage/createParty/list) 조회시 현재 파티당 참여수/참여가능수 도 데이터바인딩해야되는거같은데 데이터 추가요청드립니다.

6. 생성한 파티 상세페이지('/api/myPage/party/detail') 호출시 {"resultCode":"9999","resultMsg":"Fail","party":null,"member":null} 로 오고 있어서 확인요청드립니다.
parameter : {"partyNo":"98"}
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE2b1JjUUc2IiwiaWF0IjoxNjE0MzI0NDc4LCJleHAiOjE2MTQ0MTA4Nzh9.dVOZlVq2GESWCJFaF24TOqFrxGwU1-bP9ZXAyMtE6Z8

# 2021.03.02

1. 생성한 파티 리스트 (검색포함) (/api/myPage/createParty/list) 데이터에 총개수(totalCnt) 도 포함 요청

2. 생성한 파티 상세페이지 ('/api/myPage/party/detail') 호출시 party 데이터중 usePeriod 값이 포함되어있지 않아서 확인 요청 (api 규격서상 표기 되어있어서 확인차) 그리고 status 가 '이용기간 일수 또는 상태' 값인데 usePeriod 값으로 사용하면 되는건지 확인 요청

3. 파티 결제시 ('/api/cash/settlePayload') 500 error 발생하고 있어서 확인요청 드립니다.

4. 현재 확인시 파티결제 실패하여도 (파티참여수) totalMemberCnt값이 증가하고 있는데 같이 확인부탁드립니다

# 2021.03.03

1. 참여한 파티 상세페이지('/api/myPage/participateParty/detail') 호출시 resultCode: "9999" 로 오고 있어서 확인 부탁드립니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE0NzM3MjYxLCJleHAiOjE2MTQ4MjM2NjF9.Ajhmf0KP20X8-5lAHWZ6OHin9uTPRhqfKtZ_WFZBkgA
parameter: {"partyNo":"105"}

2. 참여한 파티 리스트 (검색포함) ('/api/myPage/participateParty/list') 호출시 리스트데이터가 partyNo가 중복되어 여러개 받아지고 있는데 데이터 확인 부탁드립니다.

3. 참여한 파티 상세페이지('/api/myPage/participateParty/detail') 호출시 결제자정보중 이름, 로그인타입(일반, 카카오, 네이버, 구글) 필요하여 추가 요청 드립니다.

4. 결제완료페이지 ('/api/cash/paymentResult') 호출시 price 값이 결제금액과 맞지 않는데 확인 요청드립니다.
1100원 파티결제에서 포인트 130 사용해서 957원 실결제후 결제완료한 값입니다.

5. 위의 파티 partyNo: 115 결제후 참여한파티 상세('/api/myPage/participateParty/detail') 데이터중 party > usePoint: 0 으로 오고 있는데 130 포인트 사용한 결제라 데이터 확인 요청드립니다.

6. 위즈톡 대화 목록('/api/chat/chatList') 호출시 500 error 발생하고 있어서 확인요청드립니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE0NzQ4OTU4LCJleHAiOjE2MTQ4MzUzNTh9.NdajN3U9SSsObB35_u_FA9-SGr-MCdQUbGV2QY8aVdI
parameter: {"partyNo":"115","buyerChatRoomId":"0ff90a30-ce79-4d58-861b-a878bf21ce9a"}
응답데이터
{"timestamp":1614753842723,"status":500,"error":"Internal Server Error","message":"\n### Error querying database.  Cause: java.sql.SQLException: Expression #1 of ORDER BY clause is not in SELECT list, references column 'wizzney.TB_CHAT.SEND_DT' which is not in SELECT list; this is incompatible with DISTINCT\n### The error may exist in class path resource [com/uniwill/wizzney/database4/chat/chatMapper.xml]\n### The error may involve com.uniwill.wizzney.database4.chat.WizzneyChatMysqlMapper.getUserInfo-Inline\n### The error occurred while setting parameters\n### SQL: SELECT DISTINCT                  CASE WHEN SENDER_ID = ? THEN SENDER_NICK                 ELSE RECEIVER_NICK                 END AS sellerNick                ,CASE WHEN SENDER_ID = ? THEN RECEIVER_NICK                 ELSE SENDER_NICK                 END AS buyerNick                ,CASE WHEN SENDER_ID = ? THEN RECEIVER_ID                 ELSE SENDER_ID                 END AS buyerWizzneyId                ,CASE WHEN SENDER_ID = ? THEN SENDER_ID                 ELSE RECEIVER_ID                 END AS sellerWizzneyId         FROM    TB_CHAT         WHERE   PARTY_NO = ?                 AND CHATROOM_ID = ?         ORDER BY SEND_DT\n### Cause: java.sql.SQLException: Expression #1 of ORDER BY clause is not in SELECT list, references column 'wizzney.TB_CHAT.SEND_DT' which is not in SELECT list; this is incompatible with DISTINCT\n; uncategorized SQLException; SQL state [HY000]; error code [3065]; Expression #1 of ORDER BY clause is not in SELECT list, references column 'wizzney.TB_CHAT.SEND_DT' which is not in SELECT list; this is incompatible with DISTINCT; nested exception is java.sql.SQLException: Expression #1 of ORDER BY clause is not in SELECT list, references column 'wizzney.TB_CHAT.SEND_DT' which is not in SELECT list; this is incompatible with DISTINCT","path":"/api/chat/chatList"}

# 2021.03.04

1. 위즈톡 대화 목록('/api/chat/chatList') 호출시 nested exception is org.apache.ibatis.exceptions.TooManyResultsException: Expected one result (or null) to be returned by selectOne(), but found: 14 에러 발생해서 확인부탁드립니다.

2. 위즈톡에서 구매자나 판매자가 메시지 보낼때 payload 중 buyerNick : 구매자 닉네임 을 포함해야되는데 위즈톡 입장시 어떤식으로 구매자 닉네임 데이터 확인가능할까요?

3. 포인트 리스트 (검색포함) ('/api/myPage/mywizzpoint/history') 호출시 500 error 발생하고 있어서 확인부탁드립니다.
response : {"timestamp":1614835720460,"status":500,"error":"Internal Server Error","message":"\n### Error querying database.  Cause: java.sql.SQLException: ORA-01427: 단일 행 하위 질의에 2개 이상의 행이 리턴되었습니다.\n\n### The error may exist in class path resource [com/uniwill/wizzney/database/mypage/MyWizzPointMapper.xml]\n### The error may involve com.uniwill.wizzney.database.mypage.MyWizzPointMapper.wizzPointHistory-Inline\n### The error occurred while setting parameters\n### SQL: SELECT *         FROM         (SELECT  ROW_NUMBER() OVER(ORDER BY regDt DESC) AS inrnum, A.*          FROM           (SELECT             DECODE(POINT_TYPE, '6','-'||POINT,'7','-'||POINT, '8', '-'||POINT, POINT) AS point             , TO_CHAR(REG_DT,'YYYY-MM-DD HH24:MI') AS regDt             , DECODE(POINT_TYPE, '1','적립','2','적립', '3', '적립', '4', '적립', '5', '적립', '6', '사용','7','차감', '8','사용') AS pointType             , DECODE(POINT_TYPE, '1','가입 이벤트','2',(SELECT TITLE FROM TB_PARTY A WHERE A.PARTY_NO = PARTY_NO), '3', (SELECT TITLE FROM TB_PARTY A WHERE A.PARTY_NO = PARTY_NO), '4', (SELECT TITLE FROM TB_PARTY A WHERE A.PARTY_NO = PARTY_NO)               , '5' , '이벤트', '6', (SELECT TITLE FROM TB_PARTY A WHERE A.PARTY_NO = PARTY_NO), '7','1년 미사용 포인트 자동 차감', '8', '출금신청') AS title           FROM TB_POINT_HIST           WHERE WIZZNEY_ID = ?           AND DEL_YN='N'                     )A)         WHERE inrnum between ? and ?\n### Cause: java.sql.SQLException: ORA-01427: 단일 행 하위 질의에 2개 이상의 행이 리턴되었습니다.\n\n; bad SQL grammar []; nested exception is java.sql.SQLException: ORA-01427: 단일 행 하위 질의에 2개 이상의 행이 리턴되었습니다.\n","path":"/api/myPage/mywizzpoint/history"}

4. 포인트리스트('/api/myPage/mywizzpoint/history') 검색단어 포함해서 호출시 500 error 발생하고 있어서 확인 부탁드립니다.
parameter : {startNum: 1, endNum: 20, searchWord: "검색어"}
{"timestamp":1614844066778,"status":500,"error":"Internal Server Error","message":"nested exception is org.apache.ibatis.reflection.ReflectionException: There is no getter for property named 'searchText' in 'class com.uniwill.wizzney.mypage.vo.MyWizzPointListRequestVo'","path":"/api/myPage/mywizzpoint/history"}

# 2021.03.05

1. 파티 결제 페이지('/api/party/subscribe') 호출시  resultCode: "9999", resultMsg: "Fail" 로만 오는데 확인요청

2. 마이페이지 > 캐시/포인트 중 N 마크 여부는 어떻게 데이터 받아야하는지 확인

3. 

# 2021.03.08

1. 위즈톡 대화 목록('/api/chat/chatList') 호출시 구매자쪽에서 한번이라도 메세지를 보내야 데이터 받아올수 있는데, 최초 위즈톡 입장시에 판매자 닉네임은 어떻게 받을수 있나요?

2. 참여한 파티 취소/환불 편집(''/api/party/cancelRefundModify) 호출시 파라미터로 seq 데이터는 어디서 확인할수 있나요?

3. 참여한 파티 분쟁취소('/api/party/cancelRefundDelete') 호출후에도 참여한 파티 상세페이지('/api/myPage/participateParty/detail') 데이터중 conflict status: 0 (진행중) 으로 오고 있어서 확인 부탁드립니다.
참여한 파티 분쟁취소('/api/party/cancelRefundDelete') 호출시 parameter: { seq: 2 }

4. 생성한 파티 멤버 상세페이지('/api/myPage/party/member/detail') 호출시 몇개 데이터가 규격서랑 다르게 내려오는데 확인 부탁드립니다.

5. 위즈톡 대화 목록(/api/chat/chatList) 호출시 파라미터로 buyerChatroomId 넣어야하는데 판매자 경우에 buyerChatroomId 를 어떻게 확인해야하나요?

# 2021.03.09

1. 위즈톡 관련해서 추가데이터  

2. 결제완료페이지(/api/cash/paymentResult) 에 파티정보관련한 표시부분의 데이터가 필요해서 추가요청드립니다.

3. 참여한 파티리스트(/api/myPage/participateParty/list) 호출시 taehoon.kim@appg.co.kr과 kakao sns 계정에서 resultCode: "9999" 로 오고 있는데 확인부탁드립니다.

4. 생성한 파티 멤버 상세페이지  (/api/myPage/party/member/detail) 호출시 resultCode:9999 로 오고 있어서 정상인지 확인부탁드립니다.
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjE2b1JjUUc2IiwiaWF0IjoxNjE1MjczNDkyLCJleHAiOjE2MTUzNTk4OTJ9.s_HBxTJ51t0xnI21pEopTgBhNSdN9bDOMmykaJMa4EA
parameter : {"partyNo":"141","memberNo":"1"}

5. 참여한 파티 상세 (/api/myPage/participateParty/detail) 호출시 양도 파티인 경우 '결제승인' 여부를 알수 있는 데이터값이 필요할꺼같은데 추가 가능할까요?

# 2021.03.10

1. 7-7 생성한 파티 취소/환불, 7-8 생성한 파티 신청반려, 7-9 생성한 파티 신청반려 편집 api 호출시 seq 필요한데 어디서 확인할수 있는건가요?

2. 패널티 게시판 리스트 (검색포함) (/api/myPage/penalty) 호출시 searchWord 값을 넣어 호출하면 resultCode: 9999 발생하는데 확인부탁드립니다.

3. 생성한 파티 멤버 상세페이지('/api/myPage/party/member/detail') 호출시 confilct 데이터중 state 값이 null 로 오고 있는데 확인부탁드립니다.

4. 6-2 참여한 파티 상세페이지, 7-10 생성한 파티 멤버 상세페이지 api 데이터중 직접분쟁신청하고 취소한경우 구분이 필요한데, conflict status 에서 진행 상태(0: 진행중, 1: 승인됨, 2: 반려됨) 외에 분쟁취소 상태 구분값도 추가가능할까요? 

# 2021.03.11

1. 위즈톡 화면에서 파티제목이 필요해서 위즈톡 대화 목록(/api/chat/chatList ) 데이터중에 제목 추가 가능할까요?

2.

# 2021.03.18

1. 4-2 파티 알림 설정 등록 한후, 파티 알림 설정한 내용를 확인하는 api 는 없나요? 그리고 파티알림설정 삭제도 필요할거 같은데 확인부탁드립니다.

2. 캐시 리스트 (검색포함)('/api/myPage/myWizzCash/cashHistory') 호출시 500 error 발생하고 있어서 로그확인부탁드립니다.
### Error querying database.  Cause: java.sql.SQLSyntaxErrorException: ORA-00904: "C"."PARTY_NO": 부적합한 식별자

### The error may exist in class path resource [com/uniwill/wizzney/database/mypage/MyWizzCashMapper.xml]
### The error may involve com.uniwill.wizzney.database.mypage.MyWizzCashMapper.getCashHistoryCount-Inline
### The error occurred while setting parameters
### SQL: SELECT       COUNT(SEQ)      FROM (       SELECT        (SELECT p.TITLE FROM TB_PARTY p WHERE p.PARTY_NO=c.PARTY_NO) AS title       FROM        TB_CASH_HISTORY       WHERE        WIZZNEY_ID = ?        AND DEL_YN = 'N'      )
### Cause: java.sql.SQLSyntaxErrorException: ORA-00904: "C"."PARTY_NO": 부적합한 식별자

; bad SQL grammar []; nested exception is java.sql.SQLSyntaxErrorException: ORA-00904: "C"."PARTY_NO": 부적합한 식별자
parameter : {"page":1}
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE2MDI4OTk3LCJleHAiOjE2MTYxMTUzOTd9.4ZfK-6oZY9sM_1kn9xQyi-pphww-gLkLfA4Zf4--bGo

3. 캐시 출금신청 페이지중 '위즈캐시출금정보', '입금받을계좌정보' 데이터를 받을수 있는 api 리스트중에 없는거 같은데 확인부탁드립니다.

4. 파티알림 내용확인, 삭제 확인했고, 출금계좌 확인 호출시 회원정보에 등록한 데이터있어도 데이터가 null 로 오고 있는데 확인부탁드립니다. 
Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE2MDQ1NTI2LCJleHAiOjE2MTYxMzE5MjZ9.kkn3YoYRfIMdQ450NOfWf0V0b6sYAKgg88HCKsyN-Xo

5. 회원정보수정에서 계좌정보 수정한뒤 /api/myPage/myWizzCash/withdrawAccountInfo 호출시
500 error 발생하는데 로그 확인 부탁드립니다.
nested exception is org.apache.ibatis.exceptions.TooManyResultsException: Expected one result (or null) to be returned by selectOne(), but found: 2

# 2021.03.19

1. 캐시 출금 신청('/api/myPage/myWizzCash/insertWithdraw') 호출시 출금액 파라미터가 필요할꺼같은데 규격서상 없어서 필요한게 맞는지 확인부탁드립니다.

2. 메인페이지 메인('/api/myPage/myMain') userInfo 데이터중 userLvNm값으로 올수 있는 'BRONZE' 이외에 무슨 값 있는지 데이터값들 문의드립니다.

# 2021.03.22

1. 미개발 api 확인요청

2. 마이페이지 > 위즈톡게시판 알림부분값 데이터값 가져오는부분이랑 알림값 변경하는 api 추가 요청 드립니다

3. 파티 알림 설정 등록('/api/party/updateHope') 후에 파티 알림 설정 정보(/api/myPage/myPartyHopeDetail), 파티 알림 리스트(/api/myPage/myHopeMatchPartyList) 호출시 500 error 발생하고 있어서 로그 확인부탁드립니다. 
nested exception is org.apache.ibatis.exceptions.TooManyResultsException: Expected one result (or null) to be returned by selectOne(), but found: 3

Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE2Mzc3OTkyLCJleHAiOjE2MTY0NjQzOTJ9.rUnxhJKtFNoWRyB4KYtvvyU1ZJLK_Uv-onSBlgEjhAQ

4. 6-5 참여파티 삭제('/api/participateParty/delete') 호출시 404 error 발생하는데 확인부탁드립니다.

5. 6-7 참여한파티 결제 승인('/api/cash/partyPaymentApproval') 호출시 500 error 발생하고 있어서 로그확인 부탁드립니다.
### Error updating database.  Cause: java.sql.SQLSyntaxErrorException: ORA-02289: 시퀀스가 존재하지 않습니다.↵↵### The error may involve com.uniwill.wizzney.database.cash.CashMapper.insertCashHistory-Inline↵### The error occurred while setting parameters↵### SQL: INSERT INTO TB_CASH_HISTORY(       SEQ       , WIZZNEY_ID       , TYPE       , ORDER_ID       , PARTY_NO       , EXIST_CASH       , CASH_AMT       , CASH       , DEL_YN       , REG_DT      )      VALUES      (       CASH_HISTORY_SEQ.NEXTVAL       , ?       , ?       , ?       , ?       , (SELECT CASH FROM TB_USER WHERE WIZZNEY_ID = ?)       , ?       , (SELECT CASH FROM TB_USER WHERE WIZZNEY_ID = ?) - ?       , 'N'       , SYSDATE      )↵### Cause: java.sql.SQLSyntaxErrorException: ORA-02289: 시퀀스가 존재하지 않습니다.↵↵; bad SQL grammar []; nested exception is java.sql.SQLSyntaxErrorException: ORA-02289: 시퀀스가 존재하지 않습니다.

Authorization: eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJXSVpaTkVZMjEwMjI0cFNzSXdPIiwiaWF0IjoxNjE2MzkzMTkzLCJleHAiOjE2MTY0Nzk1OTN9.VmIp2ECSIWLsPF4k7XfauewAaaVqWm6SpoKFALazaok
parameter : {"partyNo":"162"}

# 2021.03.24

1. 푸시발송시 각 푸시마다 json payload 값 서버에서 어떻게 보낼건지 정의된게 있나요?
