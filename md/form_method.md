# Method

<B>종류</b>

* Get
* Post

## Get

* Form 생성 시 method를 지정해주지 않으면 기본으로 get방식을 사용

```
http://localhost/method.php?id=egoing
```

* 서버쪽에 있는 method.php가 열릴때 ? 뒤에 있는 데이터를 인지해서 데이터를 처리함
* password같은 보안이 필요한 정보도 url로 전달하기 때문에 적합하지 않음

## Post

* Form tag의 method를 POST로 작성
* url에 정보가 붙지 않는다.
* 데이터를 숨겨서 전송
* Form을 이용해서 데이터를 전송할땐 POST방식을 이용