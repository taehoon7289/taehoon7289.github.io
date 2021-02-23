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
