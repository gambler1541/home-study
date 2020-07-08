# JSTL(JSP Standard Tag Library)

> JPS의 기본 태그가 아닌 JSP 확장 태그이다.

JSTL을 사용하려면 JSTL API 및 자바 구현체의 2개 라이브러리 혹은 API와 구현체가 함께 번들 형태로 구성되어있는 라이브러리가 필요하다.

## taglib 지시자 선언

자바에서 import문을 선언하듯 JSP에서도 JSTL확장 태그를 사용하려면 taglib 지시자로 라이브러리를 선언해야 한다.

다음은 JSTL core 태그 선언문이다.

```
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

JSTL은 자바에서 커스텀 태그 기능을 이용하여 활용빈도가 높은 태그를 개발, 발표한 것이 바로 자바 표준 태그 라이브러리(JSTL)이다.<br>
즉 JSTL은 표준 커스텀 태그라 할 수 있다.

JSTL은 여러 태그를 5가지 부류로 나누어  제공한다.

|분류|세부영역|접두어|URI|
|---|---|---|---|
|Core|변수지원<br>제어흐름<br>URL관리<br>출력, 예외처리|c|http://java.sun.com/jstl/core|
|XML|코어<Br>흐름제어<br>변환|x|http://java.sun.com/jstl/xml|
|Internationalization|지역화(locale)<br>메시지 포멧<br>수와 날씨 포멧<br>|fmt|http://java.sun.com/jstl/fmt|
|Database|SQL|sql|http://java.sun.com/jstl/sql|
|Functions|집합체 길이<br>문자열 처리|fn|http://java.sun.com/jstl/functions|

## 코어 태그 라이브러리

코어 태그는 JSTL에서 가장 기본이 되며 가장 많이 사용되는 태그로 변수 지원, 제어흐름, URL 관리, 예외처리, 출력을 위한 태그로 구성된다.


|분류|태그|기능|
|---|---|---|
|변수 지원|remove<br>set|이미 설정한 변수를 삭제<br>범위에서 사용할 변수를 지정|
|제어 흐름|choose<br><br>when<br>otherwise<br><br>foreach<br>forTokens<Br>if|태그 &lt;when>과 &lt;ortherwise>로 구성되어 있는 여러개의 조건속에서 하나만 선정하여 처리<br>&lt;choose>태그의 서브 태그로 조건이 true이면 실행<br>&lt;choose>태그의 서브 태그로 이전의 &lt;when>에서 조건이 모두 false이면 &lt;otherwise>내용을 실행<br>다양한 콜렉션 유형에서 반복을 처리<br>문자열을 구분자로 구분하여 토큰으로 나누어 처리<br>조건이 true이면 실행|
|URL 관리|import<br>param<br><br>redirect<br>url|다른 페이지를 현재 위치, 또는 변수에 저장<br>태그&lt;import>&lt;redirect>&lt;url>의 서브 태그로 매개 변수 전송 처리<br>새로온 URL로 이동 처리<br>질의 매개 변수를 이용하여 URL 생성|
|예외처리|catch|예외 처리|
|출력|out|출력 처리|

## Set 속성

|속성|기본값|자료 유형|기능|
|---|---|---|---|
|var||String|값이 저장되는 변수름|
|target||String|값이 저장되는 자바빈즈 객체 이거나 또는 MAP자바빈즈의 경우 setter인 property에 의해 값 지정|
|value||String|변수 또는 객체에 저장할 값|
|property||String|target 객체의 property 이름|
|scope|page|String|변수가 효력을 발휘하는 영역으로 page,request,session,application 중 하나를 지정|

## JSP 내장 객체의 영역

JSP기반의 웹 애플리케이션은 page영역, request영역, session영역, application영역 네 가지로 나누어집니다. 각각의 영역에 관한 정보는 영역과 연결된 내장 객체를 이용하여 접근할 수 있습니다.

|영역|내장객체|의미|
|---|---|---|
|page|pageContext|하나의 JSP 페이지 내에서 속하는 영역으로,<br>하나의 JSP페이지 안에서만 공유할 값을 저장합니다.|
|request|request|한 번의 요청에 대한 정보가 저장되는 영역<br>웹 브라우저가 요청을 보낼 때마다 새로운 request영역이 되고 request객체를 이용하여 모든 JSP페이지에서 접근이 가능합니다.|
|session|session|한 명의 사용자와 관련된 정보가 저장되는 영역입니다.<br>사용자가 이용하는 웹 브라우저 하나 당 영역이 존재하기 때문에 주로 로그인 정보를 저장합니다.|
|application|application|모든 사용자가 이용할 수 있는 정보를 저장하는 영역입니다. 하나의 웹 어플레킹션에 대한 요청, 세션 등과 같은 모든 정보는 application 영역에 속합니다. 주로 웹 어플리케이션의 설정 정보를 저장합니다.|

## &lt;c:choose> 태그

&lt;c:choose>태그는 조건에 따른 여러곳으로 분기 가능하고, 조건이 맞은 것이 없을 경우 기본 분기를 제공할 수 있습니다.

```
<c:choose>
	<c:when test="${name eq '김철수'}"> ... </c:when>
	<c:when test="${name eq '김영희'}"> ... </ㅊ:when>
	<c:otherwise> ... </c:otherwise>
</c:choose>
```

위 코드는 이름이 '김철수', '김영희'일 경우 분기 하고 그 외의 경우에는 &lt;c:otherwise>로 분기합니다.


## 논리 연산자

* and(&&) : 모두 참일때 참이 됩니다.
	
	* &lt;c:if test="${a > b and c < d}">
	* &lt;c:if test="${a > b && c < d}">

* or(||) : 둘중 하나라도 참이면 참이 됩니다.

	* &lt;if test="${a > b or c < d}">
	* &lt;if test="${a > b || c < d}">

* not(!) : 논리를 반전합니다.
	
	* &lt;if test="${not a == ''}">
	* &lt;if test="${!a == ''}">

* ne(!=) : 문자열 또는 숫자가 다르면 참입니다.
	
	* &lt;if test="${name != '홍길동'}">
	* &lt;if test="${name ne '홍길동'}">

	* &lt;if test="${num != 5}">
	* &lt;if test="${num ne 5}">