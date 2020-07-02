# JDBC 프로그래밍
> Java DataBase Connectivity

자바 프로그램에서 데이터베이스와 연결하여 데이터베이스 관련 작업을 할 수 있도록 해주는 자바 프로그래밍 인터페이스를 위한 API(Application Programming Interface) 규격이다.
<br><br>
JDBC는 Driver, DirverManager, Connection, Statement, PreparsedStatement, ResultSet, ResultSetMetaData, Types, DataSource등 여러개의 클래스와 인터페이스로 구성된 페이지 java.sql과 javax.sql로 구성되어 있다
<Br><br>
JDBC는 다음과 같은 데이터베이스 기능을 지원하기 위한 표준 API를 제공한다.

* 데이터베이스를 연결하여 테이블 형태의 자료를 참조
* SQL 질의
* SQL 문의 결과를 처리

## JDBC의 역할

ODBC는 JDBC보다 먼저 마이크로 소프트 회사가 개발한 것으로 c 또는 c++ 등의 언어를 이용하여 DMBS에 독립적으로 데이터베이스 프로그램을 가능하도록 하는 API 규격이다. JDBC도 ODBC와 마찬가지로 DBMS의 종류에 상관없이 쉽게 SQL문을 수행하고 그 결과를 처리할수 있도록 설계되어 있다.
<br><br>
DMBS에 독립적인 프로그램을 가능하도록 하려면 JDBC와 함께 JDBC Driver도 필요하다.
<br><br>
## JDBC driver 종류
JDBC Driver는 JDBC 인터페이스에 맞추어 해당 DMBS에서 JDBC관련 API호출이 가능하도록 관련 인터페이스와 클래스를 구현한 클래스 라이러리 이다.

* JDBC-ODBC 브릿지 드라이버
* Native API 드라이버
* Net-Protocol 드라이버
* Native-Protocol 드라이버

## JDBC프로그래밍 절차

1. JDBC 드라이버 로드

	```
	 Class.forName("oracle.jdbc.driver.OracleDriver")
	```	
	* 인터페이스 드라이버(interface driver)를 구현(implements)하는 작업으로, `Class` 클래스의 forName() 메소드를 사용해서 드라이버를 로드한다. `forName(String className)` 메소드는 문자열로 `주어진 클래스나 인터페이스 이름을 객체`로 리턴한다.
	
2. 데이터베이스 연결
	
	```
	 String dbURL = "jdb:oracle:thin:@localhost:1521:ORCL";
	con = DriverManager.getConnection(dbURL,"scott","tiger");
	```
	* Connection 객체를 연결하는 것으로 DriverManager에 등록된 각 드라이버들을 getConnection(String url)메소드를 사용해서 식별한다. 찾지못하면 no suitable error가 발생한다.

3. SQL을 위한 Statement 객체 생성
	
	```
	PreparedStatement pstmt = null;
	pstmt = con.prepareStatment(sql);
	```
	
	* sql 쿼리를 생성/실행하며, 반환된 결과를 가져오게 할 작업 영역을 제공한다.
	* Statement 객체는 Connection 객체의 createStatement()메소드를 사용하여 생성된다.
	
4. SQL 문장 실행
	
	```
	String sql = "select * from student";
	ResultSet result = executeQuery(sql);
	```
	
	* Statement 객체가 생성되면 Statement 객체의 executeQuery()메소드나 executeUpdate()메소드를 사용해서 쿼리를 처리한다.
		* stmt.executeQuery : record 반환 => Select 문에서 사용
		
		```
		ResultSet rs = stmt.executeQuery("select * from 소속기관");
		```
		* stmt.executeUpdate() : 성공한 row 수 반환 => Insert, Update, Delete문에서 사용

		```
	String sql = "update member1 set password = '3579' where id = 'abc'";
		stmt.executeUpdate(sql);
		```
		
	* 객체 Statement에서 SQL질의 문장을 실행하는 메서드
	
	|메서드 종류|반환 자료형|특징|
	|---|---|---|
	|executeQuery()|ResultSet|select와 같이 데이터베이스에 변경을 주지 않는 SQL 문장을 실행할때 사용하며 그 결과로 ResultSet 객체를 반환|
	|executeUpdate()|int|insert, update, delete와 같이 데이터베이스의 구조또는 값을 변경시키는 질의<br> create,drop과 같은 DDL구문을 사용할때 사용<Br>질의 수행 후 영향을 받은 행의 수를 정수로 반환|
	|execute()|boolean|실행할 SQL문이 어떠한 종류의 것인지를 모를 경우에 사용<br>결과가 ResultSet이면 `true` 결과가 행의 수 또는 없으면 `false`|
		
5. 질의 결과 ResultSet 처리
	
	```
 while(result.next())
 	String col1 = result.getString(1);
 	
	```
	* executeQuery() 메소드는 결과로 ResultSet을 반환한다.
	이 ResultSet으로부터 원하는 데이터를 추출하는 과정을 말한다.
	
	* 데이터를 추출하는 방법은 ResultSet에서 한 행씩 이동하면서 getXxx()를 이용해서 원하는 필드 값을 추출하는데, 이때 rs.getString("name") 혹은 rs.getString(1)을 사용한다.
	* ResultSet의 첫 번째 필드는 1부터 시작한다.
	* 한 행이 처리되고 다음 행으로 이동 시 next() 메소드를 사용한다.
	
	```
	while(rs.next()){
		out.println(rs.getString("id"));
		out.println(rs.getString("password"));
	}
	```
	
6. JDBC 객체 연결 해제 
	
	```
	result.close();
	pstmt.close();
	con.close();
	```