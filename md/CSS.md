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
			,,,
	}
</style>
```

* `.`으로 class를 선택할 수 있다.

## 자식, 자손 선택자


