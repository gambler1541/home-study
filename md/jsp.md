# JSP 문법의 기본

## 태그의 이용

JSP는 태그를 이용하여 고유한 문법을 기술하는 서버 프로그래밍 방식이다.
<br>
JSP의 태그 방식은 Script Tag와 Action Tag, Custom Tag로 나뉜다.<br>

## Script Tag

|종류|태그형식|사용용도|
|---|---|---|
|Directives(지시어)|<%@ ~ %>|JSP 페이지의 속성을 지정|
|Declaration(선언)|<%! ~ %>|소속 변수 선언과 메소드 정의|
|Expreesion(표현식)|<%= ~ %>|변수, 게산식, 함수 호출<br>결과를 문자열 형태로 출력|
|Scriptlet(스크립트)|<% ~ %>|자바 코드를 기술|
|Comments(주석)|<%-- ~ --%>|JSP 페이지의 설명을 추가|