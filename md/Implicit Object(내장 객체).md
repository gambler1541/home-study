# Implicit Object(내장 객체)

내장 객체란 JSP 페이지의 스크립트릿과 표현에서 선언 없이 사용할수 있는 객체 변수를 말한다.<br>
즉 웹 브라우저의 출력에 이용하던 객체 변수 out은 JSP 서블릿의 _jspService() 메소드에서 자동으로 선언 되므로 JSP 페이지의 스크립트릿에서 선언 없이 out.println()을 사용할 수 있었다.<br>
<br>


|내장객체|소속 패키지|클래스 이름|용도|
|----|---|---|---|
|request|javax.servlet.http|\<i> HttpServletRequest|클라이언트 요청에<br> 의한 폼 양식 정보 처리|
|response|javax.servlet.http|\<i> HttpServletResponse|클라이언트 요청에 대한 응답|
|session|javax.servlet.http|\<i> HttpSession|클라이언트에 대한 세션 정보 처리|
|application|jvax.servlet|\<i> ServletContext|웹 어플리케이션 정보 처리|
|config|javx.servlet|\<i> ServletConfing|현재 JSP 페이지에 대한 환경 처리|
|exception|java.lnag|\<i> Throwable|예외 처리를 위한 객체|
|page|java.lang|\<c> Object|현재 JSP 페이지에 대한 클래스 정보|
|pageContext|javax.servlet.jsp|\<c> PageContext|현재 JSP 페이지에 대한 페이지 컨텍스트|
|out|javax.servlet.jsp|\<c> JspWriter||