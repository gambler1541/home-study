## Media query

> 여러 기기들의 상태에 따라 다른 디자인을 할 수 있게함

```
<style>
@media (width:500px) { // midia query를 알리는 태그
	body{
		background-color : red;
	}
}
</style>
```

* 화면의 크기가 500px이 되었을때, background-color를 red로 한다.
* @media(x) : x에 max-width : 500px를 하면 500px이하일때, min-width : 500px를 하면 500px 이상일때를 뜻함
	* 브라우저는 나중에 나온 코드를 실행시킨다.
		* cascading에 의해 실행

		
```
<meta name="viewport" content="width=device-width, initail-scale=1.0">
```

위 코드를 삽입하면 핸드폰 디바이스의 화면에 따라 디자인이 바뀌는 것을 확인할 수 있다.