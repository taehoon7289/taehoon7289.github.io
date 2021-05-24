# 자바 네이밍 컨벤션

**1. 파일 명명 규칙(File Name Convention Rule)**
- JAVA 소스 개발 표준안을 수립하고 통일된 작성 규칙을 통해서 가독성을 증가시키고 좋은 품질을 유지할 수 있다.
- 업무 프로젝트를 구현하기 위해서 각 Layer 별 소스 파일의 명명 규칙은 다음과 같다.
1. 패키지명은 영문소문자를 사용한다.
2. 2개 이상 단어 조합 시 Camel  규칙 적용


| class 종류 | 파일명 구성  | 위치 패키지 또는 디렉토리  | 예 |
|---|:---:|---:|---:|
| Controller | api  | <업무명>ApiController.java  |  com.cname.<업무명><업무영역>.controller | DisplayApiController.java |
|            | fo/bo | <업무명>Controller.java  |  com.cname.<업무명><업무영역>.controller | DisplayController.java |
