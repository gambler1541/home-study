# Cookie & Session


http의 비연결 특징은 클라이언트가 이전에 한 작업의 정보를 알 수 없게한다. 이러한 비연결을 보완하고 페이지 간의 지속성 서비스를 제공하기 위한 기법이 Cookie 와 Session이다.
<br>

* Cookie는 넷스케이프 사에서 제안한 방식으로 CGI프로그램 방식때부터 사용하던 클라이언트 정보 관리 기법이고 클라이언트의 사용자 컴퓨터에 정보를 저장 관리한다. 그러므로 Cookie 방식은 서버에 부하를 주지않고 사용자 정보를 관리 할수 있는 방식이다.

* Session은 JSP에서 제공하는 클라이언트의브라우저 정보 관리 기법으로 브라우저마다 각기 다른 사용자 정보를 서버에 저장하는 방법이다.<br>
즉 Session은 클라이언트 사용자별로 여러페이지 이동을 인식하며 필요한 정보를 서버에 저장하고 조회할 수 있는 방법과 세션을 관리 할 수 있는 방법을 제공한다.

## Cookie

쿠키는 서버에서 만들어진 작은 정보의 단위로 서버에서 클라이언트의 브라우저로 전송되어 사용자의 컴퓨터에 저장된다. 이렇게 저장된 쿠키는 다시 해당하는 웹 페이지에 접속할때 브라우저에서 서버로 전송될수 있다. 
<br><br>
Cookie는 패키지 javax.servlet.http 에 속하며 아래와 같은 메소드를 제공한다.

|반환형|메소드|기능|
|---|---|---|
|int|getMaxAge()|쿠키의 최대 지속 시간을 초 단위로 지정 -1 일 경우 브라우저가 종료 되면 쿠키로 만료됨|
|String|getName()|쿠키의 이름을 반환|
|String|getValue()|쿠키의 값을 반환|
|void|setMaxAge(int expiry)|쿠키의 만료 시간을 초단위로 지정|
|void|setValue(String newValue())|쿠키에 새로운 값을 설정|

<b>형식</b>

```
Cookie cookie = new Cookie("user", "korea"); => 쿠키 생성

cookie.setMaxAge(2 * 60); => 초단위 2분 설정
```

## Session

클라이언트의 정보를 클라이언트 PC에 저장하는 것이 Cookie라면 클라이언트의 브라우저마다 각기 다른 정보를 저장하는 것이 Session 이다.

즉 세션은 클라이언트 사용자 별로 여러 페이지 이동을 인식하며, 필요한 정보를 서버에 저장하고 조회 할수 있는 방법과 세션을 관리할 수 있는 방법을 제공한다.

<b>내장 객체 session</b>

내장 객체 session은 javax.servlet.http에 속하는 인터페이스 HttpSession이다.

내장 객체인 session은 세션 자체인 식별자와 생성시간 정보를 제공하는 메소드인 getId(), getCreateion() 등을 제공한다.

|반환형|메소드|기능|
|---|---|---|
|long|getCreationTime()|1970년 1월 1일 0시를 기준으로 현재 세션이 생성된 시간까지 지난 시간을 계산하여 밀리세컨드로 반환|
|String|getId()|세션에 할당된 유일한 식별자(ID)를 String타입으로 반환|
|int|getMaxInactiveInterval()|현재 생성된 세션을 유지하기 위해 설정된 최대 시간을 초의 정수값으로 반환 지정하지 않으면 기본값으로 1800초 즉 30분이며 기본값도 서버에서 설정 가능하다.|

<b>메소드</b>

|반환형|메소드|기능|
|---|---|---|
|Object|getAttribute(String name)|name이란 이름에 해당하는 속성값을 Object 타입으로 반환, 해당하는 이름이 없을 경우에는 null을 반환|
|Enumeration|getArrtubuteNames()|속성의 이름들을 Enumeration 타입으로 반환|
|void|invalidate()|현재 생성된 세션을 무효화 시킴|
|void|setAttribute(String name, Object value)|name으로 지정한 이름에 value할당|
|void|removeAttribute(String name)|name으로 지정한 속성값 삭제|
|void|setMaxInactiveIntervar(int interval)|세션의 최대 유지 시간을 초 단위로 설정|
|boolean|isNew()|세션이 새로 만들어 졌으면 true 이미 만들어진 세션이면 false|