# Statement

Statement란 실제 데이터베이스에 SQL문을 보내기 위해 필요한 객체이다. 삽입,수정,삭제,검색을 처리하는 DML문을 사용할떄는 이 인터페이스를 사용한다.
이 객체는 Connection객체의 연결 정보를 가져와서 DB에 접근하므로 이 객체를 사용하기 위해서는 접속 상태인 Connection 객체가 먼저 존재해야 한다. Statement 객체에서 자주 사용하는 메소드는 다음과 같다.

|메소드|설명|
|---|---|
|executeQuery(SQL)|SELECT문을 실행할때 사용한다<br>ResultSet 반환|
|executeUpdate(SQL)|삽입, 수정, 삭제와 같은 SQL문을 실행한다.<br>적용된 행수를 반환한다.|
|close()|Statement 객체를 반환할때 사용한다.|

## PreparedStatement

PreparedStatement 객체가 하는 일은 Statement 객체와 비슷하다.