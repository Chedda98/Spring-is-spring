## Welcome Page 만들기(정적 페이지)
루트 : `resources/static/index.html`
```
<!DOCTYPE html>
<html>
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
Hello
<a href="/hello">hello</a>
</body>
</html>
```
- 스프링 부트가 제공하는 Welcome Page 기능
  - `static/index.html` 을 올려두면 Welcome Page 기능을 제공한다.
  ![웰컴페이지](https://user-images.githubusercontent.com/68318945/118091897-5b548000-b406-11eb-8c3b-8144b8a5d773.png)
  - [Spring Boot Features](https://docs.spring.io/spring-boot/docs/current/reference/html/spring-boot-features.html#boot-features)

## thymeleaf 템플릿 엔진
- [thymeleaf 공식 사이트](https://www.thymeleaf.org/)
- [스프링 공식 튜토리얼](https://spring.io/guides/gs/serving-web-content/)
- [스프링 부트 메뉴얼 > Template Engines](https://docs.spring.io/spring-boot/docs/2.3.1.RELEASE/reference/html/spring-boot-features.html#boot-features-spring-mvc-template-engines)

![controller생성](https://user-images.githubusercontent.com/68318945/118093701-cacb6f00-b408-11eb-9606-cf3aaa45308e.png)
- `controller` 라는 `package` 생성! 이곳에서 controller와 관련된 파일을 생성하려한다.
- 스프링은 `Annotation 명시`가 반드시 필요하다! 따라서 `@Controller` 라는 어노테이션을 명시해줘야 기능을 사용할 수 있다.
- `@GetMapping` : 웹 어플리케이션에서 `"hello"`가 들어오면 이 부분 매핑해준다.

## 동작 환경 그림
![동작 환경 그림](https://user-images.githubusercontent.com/68318945/120673696-5eef9a00-c4ce-11eb-9f4f-59f1580dd72e.png)
위 그림의 구조를 보면 이해하기 쉽다. <br>
**결론:** 컨트롤러에서 리턴 값으로 문자(`hello`)를 반환하면 뷰 리졸버(`viewResolver`)가 화면을 찾아서 처리한다.
- 스프링 부트 템플릿엔진 기본 viewName 매핑
- `resources::templates/` + {ViewName} + `.html`
<br>

cf) `spring-boot-devtools`라이브러리를 추가하면, `html`파일을 컴파일만 해주면 서버 재시작 없이 View 파일 변경이 가능하다. 
<br>
(인텔리J 컴파일 방법: 메뉴 build -> Recompile)
<br>

위의 과정을 모두 거친 작고 귀여운 결과물🌟

![귀여운 결과](https://user-images.githubusercontent.com/68318945/120675073-b7736700-c4cf-11eb-80e6-31b828590dd2.png)
<br>

### 또 다른 빌드방법
인텔리J에서 빌드하는 방법 외에 또 다른 빌드 방법이 있다. 프로젝트를 만들었던 폴더로 가서 터미널을 실행시킨 후<br>
`./gradlew.bat build` (맥은 `./gradlew build`) 실행 후<br>
`build` 폴더 안 `libs` 폴더로 들어가면
18MB짜리 `hello-spring-0.0.1-SNAPSHOT.jar` 파일이 생성된 것을 확인할 수 있다.<br>
이를 이용한 `java -jar hello-spring-0.0.1-SNAPSHOT.jar` 코드를 입력하면 똑같이 스프링부트가 실행된다. (이후에 재부팅할 땐 `.jar` 파일만 실행시키면 된다.)