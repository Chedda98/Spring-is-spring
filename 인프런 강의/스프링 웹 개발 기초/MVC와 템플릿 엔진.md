## MVC
: Model, View, Controller<br>
과거에는 뷰와 컨트롤러가 나뉘지 않고 뷰에 모든 것이 담겨있었지만 뷰는 정말 화면을 그리는 용도로 쓰고 (화면과 관련된 부분) 컨트롤러는 비즈니스 로직이 담겨있는 (서버와 관련된 부분) MVC 방식이 훨씬 바람직하다.<br>

![컨트롤러 추가](https://user-images.githubusercontent.com/68318945/120781091-b12eca80-c563-11eb-8021-f21db3e5dfdc.png)
- `"hello-mvc"`을 `@GetMapping` 어노테이션을 이용해 생성한다.<br>
- `@RequestParam` 어노테이션은 `"name"`에 해당하는 값을 `param`으로 받겠다는 어노테이션이다.

![템플릿 추가](https://user-images.githubusercontent.com/68318945/120781627-34502080-c564-11eb-9520-796689a0f0ec.png)
- `template 폴더` 하위에 `hello-template.html 파일` 내용은 스프링부트가 실행됐을 때 정적 컨텐츠와 같이 페이지 리소스 결과가 그대로 나오지 않고 `밑줄 친 부분이 변환`되어 나온다.<br>

구조를 그림을 통해 이해해보자!

![mvc, 템플릿 이미지](https://user-images.githubusercontent.com/68318945/120782489-03242000-c565-11eb-9e4c-85386411ad65.png)
- 위 사진은 name에 spring을 입력했지만 나는 `dain`을 입력했다.
- 스프링 컨테이너에서 웹 브라우저로 전달하는 과정에서 `변환`하는 과정이 있다!

참말로 이런 흐름을 거치는지 페이지 창을 통해 확인해보자

![귀여운 MVC 결과](https://user-images.githubusercontent.com/68318945/120783005-8fcede00-c565-11eb-9f74-497a64b75713.png)<br>
- `hello-mvc`만 입력하면 페이지 오류가 뜬다.
- `param`으로 값을 받을 때는 뒤에 `?` 를 붙인 다음 아까 위에서 `@RequestParam 어노테이션`으로 정의한 `name 객체`를 이용해야한다.
- 이후 `=` 뒤에 넣고자하는 문자를 넣으면 웹 브라우저에 정상적으로 출력된다.

이제 페이지 소스를 확인해보자!

![페이지 소스](https://user-images.githubusercontent.com/68318945/120783790-577bcf80-c566-11eb-9935-69549fb94866.png)<br>
아까 정적 컨텐츠와 다르게 변환된 것을 확인할 수 있다!!
**정적 컨텐츠와 MVC의 차이점이다!**

