# Connection Pool 사용하기 (JNDI, Context, Datasource)

기존의 웹 서버는 DB에 접근할 때마다 DB의 커넥션을 만들고, 커넥션을 해제하는 작업이 필요합니다. 이러한 작업은 DB 성능에 악영향을 끼칩니다. (= JDBC의 문제점)

따라서 커넥션을 미리 만들어놓고 요청이 들어오면 Connection Pool에서 connection을 제공하고, 작업이 끝나면 connection pool에 반납하는 과정을 거치도록 구현하면 불필요한 작업을 제거할 수 있습니다.

## DataSource

DataSource 객체는 Connection pool을 관리하는 객체입니다. 이 객체는 JNDI(Java Naming & Directory Interface)서버를 통해서 이용됩니다.


## 사용 절차

1. JNDI Server에서 lookup()메서드를 호출해 DataSource 객체를 얻습니다.
2. DataSource의 getConnection()메서드를 호출해 Connection 객체를 얻습니다.
3. Connetion을 가지고 DB질의를 수행합니다.
4. 질의가 끝나면 Connection 객체를 close()해줍니다.

## JDNI

Java Naming & Directory Interface(이하 JNDI)서비스는 `이름`에 맺어진 `객체`를 반환하는 역할을 합니다.

JDNI는 context.xml 파일에 &lt;Resource>라는 태그로 등록할 수 있습니다.

[context.xml]

```
<Resource>
	auth = "Container"
	driverClassName="com.mysql.cj.jdbc.Driver"
	url="jdbc:mysql://localhost/.testDB"
	username = "scott"
	password = "tiger"
	name="jdbc/Mysql"
	type="javax.sql.DataSource"
	maxTotal ="4"
	maxWaitMillis = "10000"

```

1. driverClassName : JDBC Driver의 경로를 입력합니다.
2. url : 접속할 DB서버의 url을 입력합니다.
3. username : DB에 로그인할 계정 ID
4. password : DB에 로그인할 패스워드
5. name : JNDI에 등록될 자원의 `이름`
6. type : JNDI에서 `이름`을 찾았을때, 연결될 `객체`->DataSource를 통해 Connection을 제어하기 떄문에 이를 지정합니다.
7. maxTotal : 생성할 Connection의 개수를 지정
8. maxWaitMillis : 커넥션이 없을 때 쓰레드가 기다리는 시간(ms), 이 시간이 끝나면 Exception이 발생합니다.

context.xml에 등록한 자원의 정보에 추가하면 좋은 옵션들이 있습니다.

```
1) removeAbandonedOnBorrw : 사용할 수 있는 커넥션이 부족해지면 DBCP(DataBase Connection Pool)은 버려진 커넥션을 찾아 복구합니다.
2) logAbandoned : 커넥션 자원이 낭비되고 있는 위치를 로그로 출력합니다.
					Connection Pool은 선택이 아닌 필수로 사용해야 하는 기술입니다.

```