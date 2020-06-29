# JavaBean

자바 빈즈는 자바 프로그램에서 특정한 작업인 비즈니스 로직을 독립적으로 수행하는 하나의 프로그램 단위 입니다.

자바뿐만 아니라 일반 프로그래밍 분야 중 큰 프로그램에서 독립적으로 수행되는 하나의 작은 프로그램을 `Component`라고 부릅니다. 그러므로 자바 빈즈는 자바 프로그램에서 컴포넌트이며 넓은 의미로 자바빈즈는 `자바의 모든 클래스`를 의미할수도 있습니다.

이러한 자바 빈즈를 활용한다면 한 번 작성된 자바빈즈는 여러 응용 프로그램에서 재 사용하며 프로그램 개발 시간을 단축 할수 있는 장점이 있습니다.

## 자바 빈즈의 구성

> 자바빈즈는 일반 자바 클래스 이다.

자바 빈즈는 member variables인 fields와 method로 구성된다. 자바빉브의 필드는 일반적으로 외부에서 참조 할수 없도록 private로 선언되며, 외부에서 자바빈즈의 필드를 참조하기 위해서는 public으로 선언된 getter, setter를 제공한다.

## 자바빈즈 태그의 사용

\<jsp:useBean id="test" class="className" /> 

&lt;ClassName test = new ClassName(); %>

위 두 코드는 동일함

&lt;jsp:useBean id="test" class="className" scope="application" />

&lt;jsp:setProperty name="test" property="name" value="홍길동">

&lt;jsp:setProperty name="test" property="name" value="홍길동" param="userName">


= <% test.setName(request.getParameter("userName")); %>
<hr>

&lt;jsp:useBean id="test" class="ClassName" scope="application" />

&lt;jsp:getProperty name="name" property="name" />

= <%= test.getName() %>