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

## Action Tag

액션 태그는 XML 스타일의 태그로 기술한 동작 기능을 수행하는 방식이며,<br>커스텀 태그는 새로운 태그를 정의하여 이용하는 방법이다.


|종류|태그형식|사용용도|
|---|---|---|
|<br><br><br>액션태그|1. \<jsp:include page="test.jsp" /><br> 2.\<jsp:forward page="test.jsp" /><br>3. \<jsp:plugin type="applet" code="test" /><br>4. \<jsp:useBean id="login" class="LoginBean" /><br>5. \<jsp:setProperty name="login" property="pass" /><br>6. \<jsp:getProperty name="login" property="pass" />|1. 현재 JSP페이지에서 다른 페이지를 포함<br><br>2. 현재 JSP페이지의 제어를 다른페이지에 전달<br><br>3. 자바 애플릿을 플러그인<br><br>4. 자바 빈 사용<br><br>5. 자바빈의 속성을 지정하는 메소드를 호출<br><br>6. 자바빈의 속성을 반환하는 메소드 호출|
|<br><br><br>커스텀 태그|\<tag:printData dbname="myDb" table="member" />|사용자가 직접 정의한 태그를 이용|

