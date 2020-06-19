## Position
> 각각의 속성의 위치를 지정

* CSS의 기본 position : `static`
	* 각각의 엘리먼트는 offset값을 무시하고 본인이 있어야 하는곳에 정적으로 위치함
* `relative` : 부모 엘리먼트를 기준으로 offset을 지정할 수 있음
* `absolute` : 절대 위치, 기본값은 부모의 위치를 기준으로 하지만 offset은 html을 기준으로 한다.
	* absolute를 position으로 준다면 부모와 무관한 태그처럼 사용됨
	* 자신의 컨탠트 크기만큼의 size를 가짐
		* width, height를 줄 수 있음
	* 부모의 position이 realative라면 부모의 위치를 기준으로 offset이 지정된다.(상위의 태그가 static이 아닌 position을 가진 부모를 기준으로 위치를 지정)

* `fixed` : 스크롤과 무관하게 엘리먼트를 고정시킬 수 있다.
	* 부모 엘리먼트는 fixed를 가진 자식과의 관계가 끊기기 때문에 자식의 크기를 뺀 만큼의 영역을 가진다.	
