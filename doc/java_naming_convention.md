# 자바 네이밍 컨벤션

**1. 파일 명명 규칙(File Name Convention Rule)**
- JAVA 소스 개발 표준안을 수립하고 통일된 작성 규칙을 통해서 가독성을 증가시키고 좋은 품질을 유지할 수 있다.
- 업무 프로젝트를 구현하기 위해서 각 Layer 별 소스 파일의 명명 규칙은 다음과 같다.
1. 패키지명은 영문소문자를 사용한다.
2. 2개 이상 단어 조합 시 Camel  규칙 적용


| class 종류 || 파일명 구성  | 위치 패키지 또는 디렉토리  | 예 |
|---|---|---|---|---|
| Controller | api  | <업무명>ApiController.java  |  com.cname.<업무명><업무영역>.controller | DisplayApiController.java |
|| fo/bo | <업무명>Controller.java  |  com.cname.<업무명><업무영역>.controller | DisplayController.java |
| Service | 공통 | <업무명>Service.java | com.cname.<업무명><업무영역>.service | DisplayService.java |
| DAO | 공통 | <업무명>DAO.java | com.cname.<업무명><업무영역>.dao | DisplayDAO.java |
| Model | 공통 | DB 테이블 이름으로 명명 | com.cname.<업무명><업무영역>.model | GoodsBase.java |
| SQL map xml | api | <업무명>Mapper.xml | src/main/resources/mapper/ | DisplayMapper.xml |
| 폴더 | 폴더명은 full name 명명 |  |  | ex) admin(O) , ad(X) |
| html, xml |  | 업무prefix.html |  | ex) stSearch.html |

**2. 코딩규칙(Coding Rule)**
2.1 공통 적용 규칙
| 구분 | 규칙 | 예 |
| --- | --- | --- |
| 객체 변수 | _ 사용금지  2개 이상 단어 조합 시 Camel 규칙 적용  의미 있는 명사로 작성 | GoodsDetails goodsDetails = displayService.getGoodsDetails(dispNo, goodsNo); |
| 변수 |  | String[] goodsList; |
| 필드 선언 |  | 상품번호 컬럼 : GOODS_NO → Model 필드 : goodsNo |
| 메소드 선언 |  | getGoodsDetails(..) {..} |
| 상수 | _ 사용금지  의미 있는 명사로 작성 | PAGE_SIZE |
