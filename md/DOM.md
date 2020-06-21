## DOM

> 문서 내에서 특정 태그에 해당하는 객체를 찾는다.

## getElementsByTagName
> 특정 tagname으로 객체를 찾음

```
<!DOCTYPE html>

```

* `var ul = document.getElementsByTagName('ul')[0];`
	* 인덱스를 붙인 이유는 getElementsByTagName은 모든 ul을 찾기 때문에 return값이 배열임

## getElementsByClassName
> 특정 class를 가진 태그를 찾음

* getElementsByTagName 처럼 return값이 배열

```
<!DOCTYPE html>
```

## getElementById
> 특정 ID를 가진 하나의 태그를 찾음

* 복수가 아닌 단 하나의 태그를 찾는다.
* 배열이 아님

```
<!DOCTYPE html>
```

## Query Selector
> CSS의 선택자를 인자로 받아 그 선택자에 해당하는 엘리먼트를 리턴

```
var qli = document.querySelector('li'); // 모든 li 엘레먼트

var qli = document.querySelector('.active') // class = 'active' 인 엘리먼트

var qli = document.qeurySelectorAll
```

* document.querySelector()는 조건에 해당하는 태그 하나만 리턴
* document.querySelectoryAll()는 조건에 해당하는 모든 태그를 배열로 리턴