자바에서 어노테이션(Annotaion)은 코드에 **메타데이터를 추가**하는 방법을 제공한다. 이 메타데이터는 컴파일 시간, 배포 시간, 또는 실행 시간에 처리될 수 있으며, 클래스, 메서드, 변수 등에 추가 정보를 제공하거나, 특정 기능을 수행하도록 지시하는 역할을 한다.
- 어노테이션을 사용하지 않아도 XML 설정이나 Java Config를 통해 동일한 기능을 구현할 수 있다.
- 다만, 어노테이션을 사용하면 코드가 더 간결하고 명확해지며, 설정 파일을 따로 관리할 필요가 없기 때문에 유지보수가 쉬워진다.

### 어노테이션의 주요 용도
1. **컴파일러에 대한 정보 제공**
	- 컴파일러에게 코드 문법 에러를 체크하도록 정보를 제공한다. 
	- 예를 들어, @Override 어노테이션은 메서드가 오버라이드 되었음을 명시하며, 만약 상위 클래스나 인터페이스에 해당 메서드가 없다면 컴파일러는 에러를 발생시킨다.
2. **코드 분석**
	- 코드를 분석하는 도구에서 정보를 제공 받는다.
	- 예를 들어, @Deprecated 어노테이션은 특정 요소가 더 이상 사용되지 않음을 나타내며, 사용 시 경고를 발생시킨다.
3. **런타임 처리**
	- 실행 시간에 어떤 행동을 하도록 정보를 제공한다.
	- 예를 들어, Spring Framework에서는 @Autowired 어노테이션을 통해 의존성 주입을 처리한다.


### 내장 어노테이션
#### 1. @Autowired
-  [[Dependency Injection]]을 **수행**하는 데에 사용된다. 주로 생성자, 필드, 세터 메서드에 적용되어 해당 위치에 **자동으로** 의존성을 주입한다.
#### 2. @Controller
- 주로 웹 페이지를 뷰(View)로 렌더링하는 게 사용된다. MVC 패턴의 컨트롤러로서 역할을 수행한다.
- 주로 사용자의 요청을 받아서 비즈니스 로직을 처리한 후, 결과를 뷰 템플릿으로 전달함여 HTML과 같은 뷰 페이지를 생성한다.
#### 3. @RestController
-  @Controller에 @ResponseBody를 추가한 것과 동일한 효과를 가진다.
- 이 어노테이션은 주로 RESTful 웹 서비스를 개발할 때 사용된다.
- 주로 데이터([[API]])를 반환하는 데 최적화되어 있으며, 별도의 뷰를 렌더링 하지 않는다.
#### 4. @GetMapping
- HTTP GET 요청을 특정 메소드에 매핑하기 위해 사용된다.
```java
		@RestController
		public class UserController {

			@GetMapping("/hello")
			public String getHello() {
				return "Hello Around Hub Studio!";
			}
		}
```
#### 5. @PostMapping
- 클라이언트로부터 HTTP POST 요청을 받아들이는 메소드에 사용된다.
- POST 요청은 주로 새로운 리소스를 생성할 때 사용된다.
#### 6. @PutMapping
- HTTP PUT 요청을 처리하는 메소드에 사용된다.
- PUT 요청은 주로 기존 리소스를 업데이트할 때 사용된다.
#### 7. @DeleteMapping
- HTTP DELETE 요청을 처리하는 메소드에 사용된다.
- DELETE 요청은 주로 리소스를 삭제할 때 사용된다.
#### 8. @PostContstruct
-  [[Bean]]의 초기화가 완료된 후 실행할 메서드를 지정할 때 사용된다.
- Spring 컨테이너가 해당 [[Bean]]을 생성하고 [[Dependency Injection]]을 완료한 후, @PostConstruct가 붙은 메서드를 호출한다.

