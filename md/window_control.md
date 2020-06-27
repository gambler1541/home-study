## 창 제어

* `window.open(url)` : 자바스크립트에서 url로 연결된 새 창을 연다.
	* window.open(url, _self) : 현재 탭에서 새 창이 열림
		* _blank : 새 탭에서 윈도우를 생성
		* HTML의 Target속성에 들어갈 수 있는 값이 들어갈 수 있다.
	* window.open('url','title') : 창에 이름을 붙일수 있다. open을 재실행 했을 때 동일한 이름의 창이 있따면 그곳으로 문서가 로드된다.
	* window.open('url','target','width','height','resizable') : width 폭, height 높이, resizeable 윈도우의 크기를 조절할 수있는지 여부(최근 브라우저들은 사용x)

