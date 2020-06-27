## HTMLElement

```
var li = document.getElementById('active');
li.constructor.name // HTMLLIElement

var lis = document.getElementsByTagName('li');
lis.constructor.name // HTMLCollection

```

* 단수일 땐 HTMLLIElement, 복수일 땐 HTMLCollection