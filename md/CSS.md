# CSS
> HTML에 style을 주는 방법


### Inline Style

```
<div style="color : red"> Inline Style Sheet </div>
```

* tag의 속성으로 style을 줌

### Style tag를 이용한 방법(Internal Style Sheet)

```
<style>
	h2 {
		color:blue;
	}
</style>
```

* head tag 사이에 style tag를 만들고 셀렉터를 이용하여 스타일을 줄 수 있다.

## 선택자와 선언

* `;`로 속성을 구분함

<a href="http://flukeout.github.io">선택자 연습</a>
##### Tag SELECTOR

```
<style>
	div {
		color : red;
		...
	}
</style>
```

####  \# ID SELECTOR

```
<style>
	li#id {
		color : red;
		text-decoration : underline;
	}

</style>

```

* `#`으로 id를 선택할 수 있다.

#### \# Class SELECTOR

```
<style>
	li.class {
			color : red;
			...
	}
</style>
```

* `.`으로 class를 선택할 수 있다.

## 자식, 자손 선택자

`tag a > tag b` : a tag에 속한 b 태그를 선택하는데, 바로 밑에 있는 태그만 선택

`tag a tag b` : tag a에 속한 tag b를 선택, 어디에 있던 속해있기만 한다면 선택

`tag a, tag b` : tag a와 tag b 둘 다 선택 

## 가상 클래스 선택자(pseudo class selector)

* 특수한 선택을 하게함
* 각각의 엘리먼트의 상태에 따라서 엘리먼트를 선택

|선택자|의미|
|---|---|
|:active|active 되있는 모든 태그|
|:visited|방문한 링크|
|:link|방문한적이 없는 링크|
|:hover|마우스가 올려진 상태|
|:focus|해당 태그가 포커싱되었을 경우|

* visited의 경우 보안상의 이유로 아래와 같은 속성만 변경이 가능
	
	* color
	* background-color
	* border-color
	* outline-color
	* The color parts of the fille and stroke properties

## ETC Selector

`*` : 모든 태그를 선택

```
tag *

해당 태그의 밑에있는 모든 태그를 선택
```	

`+` : 두 태그가 나란히 있는경우 선택

```
A + B

A 태그와 인접한(나란히 있는) B 태그를 선택
A 태그는 제외
```

`A ~ B` : A에 인접한 B를 모두 선택

```
A ~ B

A에 인접한 B를 모두 선택
+는 하나만 선택하지만 ~는 모두 다 선택한다.
```

`:first-child` : 첫 번째 자식 태그를 선택

`:only-child` : 자신이 누군가의 단독 자식일 경우 선택

`:last-child` : 태그의 마지막 자손을 선택

`:nth-child(A)` : A 번쨰 child

`:nth-last-child(A)` : 뒤에서 A번째의 태그를 선택

`:first-of-type` : tag:first-of-type의 형식으로 사용, 해당 tag의 첫번째를 선택

`nth-of-type(A)` : tag:nth-of-type(A) 형식으로 사용, 해당 태그의 a번째를 선택(even으로 짝수, odd로 홀수선택 가능)

`:nth-of-type(An+B)` : A,B는 상수가 들어가고, n에는 변수가 들어가는데, 변수는 유저가 넣는게 아니라 시스템이 넣음 

`:only-of-type` : tag:only-of-type 의 형식으로 사용, 자기 자신과 같은 타입의 sibling(형제 타입)이 존재하지 않은 태그를 선택

`:last-of-type` : tag:last-of-type의 형식으로 사용, tag의 마지막 태그를 설정

`:empty` : tag:empty 형식으로 사용, tag가 아무것도 가지고 있지 않다면 선택

`:not(X)` : not(#fancy) id값이 Fancy가 아닌 모든 것을 선택 
