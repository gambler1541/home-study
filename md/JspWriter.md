# JspWriter

내장객체 out은 클래스 javax.servlet.jsp.JspWriter 자료 유형으로 jsp 페이지의 출력을 위한 객체이다. 내장 객체 out은 출력된 버퍼링에 관련된 주요 메소드를 제공한다.

반환 값|메소드|용도
|---|---|---|
void|print(값)|여러 자료 유형 출력
void|println(값)|여러 자료 유형 출력 현재줄을 종료
void|clearBuffer()|버퍼의 현재 내용물 제거
void|flush()|현재 출력 버퍼에 저장되어 있는<br>내용을 웹브라우저에 전송하고 비운다.|
void|clear()|버퍼의 내용을 비움 이미 flush()된 경우<br>IOEception() 발생|
int|getBuffersize()|버퍼의 전체 크기 반환|
int|getRemaining()|버퍼에 남아있는 크기를 반환|
boolean|isAutoFlush()|현재 autoFlush 반환|

## Exception

예외처리 exception 객체는 페이지 지시자에 isErrorPage = true로 지정한 경우 이용할 수 있는 내부 객체이다.<br><br>
내부 객체 exception은 지정한 예외 처리 페이지에서 적절한 예외 처리를 구현한다.<br><br>

|반환값|메소드|용도|
|---|---|---|
|String|getMessage()|예외를 표시하는 문자열 반환|
|String|toString()|예외 자체 문자열 반환|
|void|printStackTrace()|표준 출력으로 스택 추적 정보 출력|