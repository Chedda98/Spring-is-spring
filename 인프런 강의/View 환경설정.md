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