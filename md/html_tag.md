<H1> HTML의 변천사와 태그사용의 통계 </h1>

<a href="http://www.martinrinehart.com/frontend-engineering/engineers/html/html-tag-history.html">태그의 변천사</a>

* HTML 태그의 변천사

<a href="https://www.advancedwebranking.com/html"> 태그의 통계</a>

* 태그사용의 통계

<h1> HTML tag </h1>


&lt;p&gt; tag는 단락을 구분한다.

<hr>

&lt;br&gt; tag는 줄바꿈을 한다.

* &lt;br&gt;태그는 내용이 없는 태그이기 때문에 닫는 태그가 없다.

* &lt;br&gt; 태그로 &lt;p&gt;태그와 같이 단락을 구분을 지을순 있지만 단지 시각적인 모습으로만 단락을 구분한것처럼 보이기 때문에 단락을 지정하기 위해서는 &lt;p&gt;태그를 사용한다.

<hr>
&lt;img&gt; tag는 웹에 이미지를 보이게 해야하는 경우 사용된다. 

* &lt;img&gt; 태그의 속성으로는 src, title, alt등이 있다.
	* src : 이미지가 있는 경로
	* title : 마우스를 올렸을때 나타나는 사진의 설명
	* alt : 경로에 이미지가 없을경우 사진 대신 나오는 대채제(text)

* <a herf="https://pixabay.com/">이미지 다운로드</a>

<hr>

&lt;table&gt; tag는 표를 만드는 태그이다.

* &lt;th&gt;태그를 이용하여 제목을 구분할수 있다.

* 표의 행은 &lt;tr&gt;로 묶고 각각의 열(데이터)는 &lt;td &gt; 태그를 사용한다.

* 과거에는 화면의 레이아웃을 구성하는데 테이블을 사용했다.

* &lt;thead&gt;, &lt;tbody&gt;,&lt;tfoot&gt; 태그는 사용하지 않더라도 브라우저가 자동으로 만들어주지만 문서를 작성할 때 해주는게 좋다.

* rowsapn : 수직(행)으로 합침
* colsapn : 수평(열)으로 합침

<hr>
&lt;form&gt; tag는 로그인을 하거나 회원가입을 하거나 물건을 살때 서버로 정보를 전달할때 사용

* 데이터를 어디에 전송할지를 정할 수 있다.
	* action속성에 작성

<hr>
&lt;input&gt; tag는 입력을 받기 위한 태그

* type : input의 타입을 정함(text, password, submit...)
* name : 서버에 전송될 때 각각의 데이터를 구분하기 위해 지정해야함
	* http://localhost/login.php?`id=egoing&password=1111&addr=부산시+사하구`
* default : inputbox에 기본으로 적혀있음

<hr>

&lt;textarea&gt; tag는 여러줄의 입력을 받을수있다.

* cols : 가로로 n글자가 입력받을 수 있을만큼 폭이 커짐.
* rows : 세로로 n줄을 입력받을 수 있을만큼 폭이 커짐
* 기본값은 value로 넣는게 아니라 textarea태그 사이에 컨탠트를 넣을 수 있다.

<hr>

&lt;select&gt; tag를 사용하면 dropdownlist(combobox)형식의 선택지가 생긴다.

* &lt;option&gt; tag로 각각의 항목을 만들수 있다.
* `value`속성으로 사람이 보는 값과 서버로 전송하는 값을 다르게 보낼수있다.
* multiple 이란 속성을 작성하면 여러개의 값을 선택할수 있게된다.
	* 다중 선택시 `color=red & color=black`형식으로 서버에 전달된다.

<hr>

&lt;radiobutton&gt; tag는 여러개 중에 하나 혹은 복수개를 선택해서 서버에 전송할수 있다. 

* 형식은 input tag의 type에 `raido`를 넣어줌
* 하나의 버튼을 누르면 다른 버튼이 선택이 풀리게 하기위해서는 버튼을 `같은 name`으로 작성해주면됨
* &lt;checkbox&gt; tag는 다중 선택을 위해사용
* `checked`속성으로 체크가 된상태로 시작하게 할 수 있다.

<hr>

<h4>&lt;hidden&gt; fleid</h4>

> UI가 필요없거나 몰래 데이터를 서버에 보내야할 경우 사용




