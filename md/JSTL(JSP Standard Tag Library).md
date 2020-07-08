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