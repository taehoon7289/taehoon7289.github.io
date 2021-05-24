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

---

**2. 코딩규칙(Coding Rule)**

*2.1 공통 적용 규칙*

| 구분 | 규칙 | 예 |
| --- | --- | --- |
| 객체 변수 | '_' 사용금지  2개 이상 단어 조합 시 Camel 규칙 적용  의미 있는 명사로 작성 | `GoodsDetails goodsDetails = displayService.getGoodsDetails(dispNo, goodsNo);` |
| 변수 |  | String[] goodsList; |
| 필드 선언 |  | 상품번호 컬럼 : GOODS_NO → Model 필드 : goodsNo |
| 메소드 선언 |  | `getGoodsDetails(..) {..}` |
| 상수 | '_' 사용금지  의미 있는 명사로 작성 | PAGE_SIZE |

*2.2 업무 Mapper Interface 메소드명 규칙*

1. 업무 Mapper 클래스의 메소드 명은 기능에 따라 다음과 같은 형태로 작성하여야 한다.
2. 업무 Mapper : 데이터 구조 종속적인 단위로 개발

| 동사 | 설명 | 예 |
| --- | --- | --- |
| insertXXX | 한 건의 데이터를 생성하는 경우 | `void insertCode(Code)` |
| updateXXX | 한 건의 데이터를 변경하는 경우 | `void updateCode(Code)` |
| deleteXXX | 한 건의 데이터를 삭제하는 경우 | `void deleteCode(Code)` |
| selectXXX | 한 건의 데이터를 조회하는 경우 | `CodeDTO selectCode(CodeDto)` |
| selectXXXList | 여러 건의 데이터를 조회하는 경우(List<DTO>리턴) | `List selectCodeList(CodeDto)` |
| updateXXXList | 여러 건의 데이터를 변경하는 경우 | `void updateCodeList(Code...)` |
| deleteXXXList | 여러 건의 데이터를 삭제하는 경우 | `int deleteCodeList(Code...)` |
| insertXXXList | 여러 건의 데이터를 생성하는 경우 | `void insertCodeList(Code...)` |
| saveXXXList | 여러 건의 데이터를 생성, 변경, 삭제 하는 경우 | `void saveCodeList(Code...)` |

---

**3.Model 개발 가이드**

*3.1 Model의 역할*
Model 객체는 Request/Response에 필요한 데이터를 담고 있는 객체이다
<br>
보통 VO, DTO  등 여러 이름으로 사용하고 있으나 현 프로젝트에서는 Model 로 통일한다 
<br>
model  객체는 주로  setter/getter 로 이루어진 POJO 객체로써 절대로  Bean객체로 생성하면 안된다 
<br>
model  객체를 사용함으로써 요청에 대한 데이터를 예상할수 있으며 또한 @Valid 같은 Validation Framework 활용도 가능하여 
<br>
효율적으로 개발할수 있다   
<br>
또한 @Data 같은   lombok 라이브러리도 활용할수 있다
<br>

```java
@Data
public class Board implements Serializable {
 
    private int num;
 
    @NotEmpty(message = "제목을 입력해 주세요")
    @Size(min = 3, max = 200, message = "제목은 최소 {min}자에서 최대 {max}자까지만 가능합니다")
    @ApiModelProperty(notes = "글제목", required = true)
    private String title;
 
    @NotEmpty(message = "내용을  입력해 주세요")
    @Length(min = 5, message = "내용은 최소  {min}자리 입니다")
    private String contents;
}
```
 
---

**3.2 Model 사용범위**

model 은 정보를 담는 기능을 하기 때문에 모든 로직에서 자유롭게 사용할수 있다 
<br>
보통 데이터베이스의 테이블과 매칭하여 사용하고자 하는  경우가 많고 1개의 model객체만 생성하여  
<br>
Request  요청 파라미터 / 데이터베이스 결과값을 담는 경향이 있는데 이는  지양한다
<br>
1개의 model 객체만으로 로직을 구현시 API 통신및 BO/FO에 전달시 불필요한 json 정보들이 많을수 있다 
<br>
따라서 Request 요청에 대응하는 model 과 Response에 대응하는 model을 각각 분리하여 사용하기를 권장한다 
<br>
이럴경우 보통 Request/Response  model 객체간에 중복 정보에 해당하는 경우가 많은데 
<br>
이럴경우 중복된 정보들은 부모객체를 생성하여 상속하여 사용하면 
<br>
효율적으로 확장하여 활용할수 있다 
<br>
프로젝트에서 Model 객체 사용을 가능한 권장한다
 
*3.3 Model package 확장*

model 객체는 프로젝트내에서 다수가 발생할수 있으며 이를 효율적으로 관리하기 위해서  package를 확장하여 사용하길 권장한다
<br>
```
예)  com.cname.lps.board.model package에서 다음과 같이 확장하여 model  객체를 관리한다 

      com.cname.lps.board.model.user

      com.cname.lps.board.model.file

      com.cname.lps.board.model.notice
```
 
*3.4 조회 조건 하에서 get/post 에서의  model  개발가이드(API)*

BO/FO에서 API로 전송하는  경우 가능한 get 방식으로 전송을 권장한다 
<br>
api 전송은 REST API 방식을 따르도록 가이드 하고 있으며 이는 get에 대해서  cache를 활용하기 위함이다 
<br>
API 서버 앞단에  API G/W 미들웨어를 연동하며 G/W에서   get 호출에 대해서 cache를 활용할수 있어 효율적이다 
<br>
따라서 parameter 갯수가 10개 미만인 경우 get 방식을 권장한다
<br>

*4. Annotation 기반 개발*

업무 컴포넌트는 Annotation 기반으로 구현하며 Layer별로 사용하는 Annotation은 다음과 같다
<br>
@SpringBootApplication : 스프링 컴포넌트 스캔 및 스프링 부트 자동 구성을 활성화 한다.
<br>
@Controller : 업무 Controller 구현 시 사용, 역할 별 객체 생성 (@RequestMapping, @ResponseBody, @RequestBody)
<br>
@Service : 업무 Service 구현 시 사용, 역할 별 객체 생성
<br>
@Repository : 업무 DAO구현 시 사용, 역할 별 객체 생성
<br>
@Autowired : DI(Dependency Injection, 의존성 삽입)을 지원하며, 객체 초기화 시 연관된 객체를 삽입시킨다.
<br>
@Mapper : DAO interface를 구현하지 않아도 SQL map xml을 호출해준다. (단, DAO의 패키지명과 SQL map xml의 네임스페이스가 동일해야함)
<br>
이외 @Component, @Qualifier, @Resource 등의 여러 종류의 Annotation이 존재하며 프로젝트 진행 중 추가적으로 유용한 Annotation을 검토하여 사용할 수 있다.
<br>
DI : Dependency Injection(의존성 삽입), Spring IOC(Inversion of Control) Container에서 지원하는 runtime 시 객체 연관 참조 삽입 기술
