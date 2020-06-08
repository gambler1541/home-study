#Meta Data

* 어떤 데이터를 설명하는 데이터
* 웹 페이지를 설명하는 정보를 필요로 할 수 있다.
	* ex) 제목을 알려주기 위한 title tag
* 웹 페이지를 설명하기 위한 부가적인 정보(웹 페이지에 표현되지는 않음)

```
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <!-- 문자의 규칙(작성한 웹페이지를 컴퓨터에 저장할때 인코딩되는 방법)의 정보 -->
    <!-- 생략하면 기본으로 설정되어있는 방식으로 인식하는데 브라우저에 따라 다르게 표시됨 -->
    <meta charset="utf-8">
    <!-- 웹 페이지의 요약자료 -->
    <meta name="description" content="인사하는 방법">
    <!-- 웹 페이지를 설명하는 키워드 -->
    <meta name="keywords" content="인사,안녕,한국어">
    <!-- 저자  -->
    <meta name="author" content="park">
    <!-- 30초마다 페이지를 refresh 함 -->
    <meta http-equiv="refresh" content="30">
    <title></title>
  </head>
  <body>
    안녕하세요?
  </body>
</html>

```

* 웹 페이지의 내용은 아니지만 그 웹페이지를 설명하는 태그
