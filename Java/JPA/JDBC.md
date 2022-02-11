# JDBC

Java Database Connectivity: 자바 프로그램이 데이터베이스와 연결되어 데이터를 주고 받을 수 있게 해주는 프로그래밍 인터페이스.

## JDBC 과정

1. DB벤더에 맞는 드라이버 로드
2. DB서버의 IP,ID PW등을 DriverManager 클래스의 getConnection 메소드를 사용하여 Connection 객체 생성
3. Connection으로 부터 PreparedStatement 객체를 받음
4. executeQuery를 수행하고 ResultSet객체를 받아 데이터를 처리
5. 사용했던 ResultSet, PreparedStatement, Connection을 close
