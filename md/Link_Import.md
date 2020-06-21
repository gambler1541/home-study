## Link

* 동일한 css를 사용하는 웹 페이지가 많은경우 하나의 코드를 수정하기 위해 모든 웹 페이지를 수정해야 하는 경우가 생긴다.

* 코드의 중복을 제거하는 방법

```
style.css

h1{
	color : powderblue;
}

```

```
link_1.html

<link rel="stylesheet" href="style.css">
```

```
link2.html

<link rel="stylesheet" href="style.css">
```

* 하나의 css파일을 만든 뒤 각 웹 페이지에 Link를 적어주면 css파일에 작성된 스타일이 웹 페이지에 공통적으로 적용된다.

## Import

```
<style>
 @import url("style.css")
</style>
```

* link태그와 똑같은 기능을 한다.