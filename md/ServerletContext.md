# ServerletContext

내장 객체 application은 javax.servlet.ServletContext 인터페이스자료 유형으로 웹 어플리케이션에서 유지 관리되는 여러 환경 정보를 관리한다. 여기서 웹 어플리케이션이란 여러개의 서블릿과 JSP로 구성되는 웹 서비스 응용 프로그램 단위로 내장 객체 application은 서블릿과 서버 간에 자료를 교환하는 여러 메소드를 제공한다.

|반환값|메소드|용도|
|---|---|---|
|String|getServerInfo()|JSP 컨테이너의 이름과 버전정보
|Object|getAttribute(String name)|웹에서 지정한 이름의 속성을 반환
|void|log(String msg)|지정한 MSG의 로그를 저장
|void|setAttribute(String name, Object object)|웹에서 지정한 이름으로 오브젝트를 저장
|void|removeAttribute(String name)|웹에서 지정한 이름의 속성을 삭제