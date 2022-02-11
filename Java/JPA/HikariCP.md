# HikariCP

HikariCP란 Springboot 2.0부터 default로 설정되어 있는 DB Connection Pool로써 Zero-Overhead가 특징으로 높은 성능을 자랑하는 DB Connection Pool

## 필요성

-   기존 JDBC 의 경우 Java application과 Database가 연동되는 데이터를 처리하는 과정 중 Connection 객체를 얻는 부분이 오래 걸림.
-   사용자가 급증하는 서버 환경에서는 반복적으로 Connection 객체를 얻기 위해 많은 시간을 소모.
-   따라서 미리 필요한 양만큼의 Connection 객체를 미리 얻어 놓음으로써 대기 시간과 네트워크의 부담을 줄임.
-   DB Connection Pool

<img src="https://media.vlpt.us/images/hoyun7443/post/749582a1-39ab-4cf9-815c-ceb07db65a37/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(3).png">
