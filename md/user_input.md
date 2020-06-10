# User_Input(Form)

## input types
* color  
* date 
* datetime 
* datetime-local  
* email 
* month 
* number
* range
* search
* tel
* time
* url
* week

## Input tag의 속성

* autocomplete = on / off
	* 자동 완성기능이 활성화됨(비활성화됨)
* placeholder = "value"
	* text에 value값이 기본값으로 나타나게됨 
* autofocus
	* 사용자의 커서가 이 옵션이 있는 곳으로 감
* required
	* 유효성 검사(필수 입력)
* pattern = "정규표현식"
	* 해당 입력값의 패턴을 검사함
	* pattern = "[a-zA-Z]"
		* 대괄호안에 있는 표현식이 알파벳 하나를 의미함
		* 정규 표현식에서 '.'은 모든 것을 의미
		* '+' :  하나 이상을 의미
		* 	[0-9] : 숫자를 의미