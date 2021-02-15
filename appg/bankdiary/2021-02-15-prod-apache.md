# 스탠다드 운영서버 Apache 관련 문의내용

1. /usr/local/apache/conf/httpd.conf 내용중 
line 511 :: LoadModule deepfinder_module /usr/local/deepfinder/lib/mod_deepfinder24.so
mod_deepfinder24.so 모듈이 있는데
이 모듈로 인해 api 호출시 GET, POST 방식의 api 요청/응답은 정상적이며, PATCH, DELETE method 방식 api가
302 으로 응답되는 경우가 발생하고 있음.
-> PATCH, DELETE method 를 포함하는 api 를 사용중이라, PATCH, DELETE method 의 허용여부가 가능한지 확인필요

2. 스탠다드 코드중 웹소켓(Web socket)을 사용하는 부분이 있어, 
# LoadModule proxy_wstunnel_module modules/mod_proxy_wstunnel.so
mod_proxy_wstunnel.so 라는 apache module 을 추가해야함.
-> 현재 설치된 module중에 포함되어있지 않아, 모듈 추가요청 가능한지 확인필요
