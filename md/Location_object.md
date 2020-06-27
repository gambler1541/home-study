## Location Object
> 현재 브라우저에 열려있는 문서의 URL을 알려주는 객체

* `location.toString`, `location.href`를 사용하면 둘다 똑같은 값이 리턴된다. 
	* 더 정확한 값은 `href`

* `location.protocol`: 해당 페이지의 프로토콜을 보여줌
* `host/port`
* `pathname`
* `search` : url의 ?뒤에 나오는 문자(서버에 전달된 값)
* `bookmark` : url의 #뒤에 나오는 문자

```
http://opentutorials.org:80/module/1?id=1#hash

http : protocol
opentutorials.org : host
80 : port
modeul : pathname
?id : search
#hash : bookmark
```

* location객체는 현재 브라우저의 정보만 알려주는게 아니라 변경, 리로드가 가능하다.

```
location.href = "url"; // url로 이동
location = "url"; // 위와 같은 효과를 내지만 위 의 방법이 좀 더 명시적이다.
location.href = location.href // 현재 url을 리로드한다.
location.reload() // 위와 동일
```