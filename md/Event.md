# Event

> 사용자가 클릭 했을 때, 스크롤을 했을 때, 필드의 내용을 바꾸었을 때를 의미

* `event target` : 이벤트의 대상이되는 태그
* `onclick` : 이벤트 타입
* `event handler` : 이벤트가 발상했을때 실행되는 코드

## inline 방식으로 이벤트를 등록
> 이벤트를 이벤트 대상의 태그 속성으로 지정하는 것

```
<input type="button" onclick=alert('hello world';)>
```

* this를 통해서 간편하게 참조할 수 있다.
	 * this는 이벤트 타겟

* 어떤 태그가 있을때 그 태그에 해당하는 이벤트가 무엇인지 태그에 직접 기술되어 있기 때문에 쉽게 찾을 수 있다는 장점이 있다.
* HTML은 정보를 표현하기 위한 수단인데, 자바스크립트의 코드가 HTML태그에 직접 기술되어 있으면 정보로서의 가치가 떨어질수 있다.

## Property Listener

> 이벤트 대상에 해당하는 객체의 프로퍼티로 이벤트를 등록하는 방식

```
<body>
	<input type="button" id="target" value=""button>

<script>
	var t = document.getElementById('target');
	t.onclick = function(event){
		alert('Hello world, ' + event.target.value);
	}
</script>	
```

## addEventListener
> 이벤트를 등록하는 가장 권장되는 방식, 이 방식을 사용하면 여러개의 이벤트 핸들러를 등록할 수 있다.

```
<script>
vat t = documen.getElementById('target');
t.addEventListener('click', function(event){
		alert(1);
})

</script>
```