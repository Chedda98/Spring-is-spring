## @ResponseBody
스프링에서의 Body가 아니라 `HTTP에서의 Body` 부분만 나타낸다. 즉, 응답 부분의 Body가 바뀌는 것이다!

![api 예시 캡쳐](https://user-images.githubusercontent.com/68318945/120928718-ce5cc800-c720-11eb-92a4-11c437db88c0.png)<br>
겉으로 보기에는 MVC와 뭐가 다른지 모르겠다. 페이지 소스를 살펴보자!<br>
![api 예시 페이지 소스](https://user-images.githubusercontent.com/68318945/120928759-05cb7480-c721-11eb-996a-d0d7763db702.png)<br>
HTTP에서 온전히 `데이터만 넘어오는 것`을 확인할 수 있다!<br>
하지만 이 API 방식은 잘 쓰이지 않는다. (진짜는 따로 있다)<br>

`cf1) 꿀팁 : ctrl + shift + enter == 코드 자동완성`
`cf2) Alt + insert == Getter & Setter 추가 단축키`