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
