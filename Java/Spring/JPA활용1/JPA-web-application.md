# JPA 활용 1 - 웹 애플리케이션 개발

## 주의사항

-   [x] : `H2 database` version 1.4.200
-   [x] : jUnit4 적용 -> jUnit5를 사용하려면 잘 알고 사용하기
-   [x] : `lombok` setting
-   [x] : Build and run using: `Gradle` -> `intelliJ IDEA`

<br />

## 라이브러리

-   spring-boot-starter-web
    -   spring-boot-starter-tomcat: 톰캣 (웹서버)
    -   spring-webmvc: 스프링 웹 MVC
-   spring-boot-starter-thymeleaf: 타임리프 템플릿 엔진(View)
-   spring-boot-starter-data-jpa
    -   spring-boot-starter-aop
    -   spring-boot-starter-jdbc
        -   HikariCP 커넥션 풀 (부트 2.0 기본)
    -   hibernate + JPA: 하이버네이트 + JPA
    -   spring-data-jpa: 스프링 데이터 JPA
-   spring-boot-starter(공통): 스프링 부트 + 스프링 코어 + 로깅
    -   spring-boot
        -   spring-core
    -   spring-boot-starter-logging
        -   logback, slf4j

<br />

## Entity

database에 쓰일 필드(entity 각 column)와 여러 entity 간 연관관계 정의.

-   `@Entity`: 이 클래스가 entity 임을 알려줌. JPA에서 정의된 필드들을 바탕으로 데이터베이스에 테이블을 생성.
-   `@Id`: 해당 엔티티의 주요 키가 될 값을 지정
-   `@GeneratedValue`: Pk가 자동으로 1씩 증가하는 형태로 생성될지 등을 결정

<br />

## Repository

Entity에 의해 생성된 DB에 접근하는 메서드들을 사용하기 위한 인터페이스.

-   findAll()
-   CRUD

<br />

## Service

Model(Entity)이 데이터 베이스에 받아온 데이터를 전달받아 가공.

-   `django`에서 service layer를 두는 것과 비슷

<br />

## SpringBootTest

@SpringBootTest 어노테이션을 통해 스프링부트 애플리케이션 테스트에 필요한 거의 모든 의존성 제공

<br />

## 연관관계의 주인

-   두 객체 연관관계 중 하나를 정해서 테이블의 외래키를 관리

### 규칙

-   연관관계 주인만이 database 연관관계와 매핑
-   연관관계 주인만이 외래키를 관리(등록, 수정, 삭제)
-   주인이 아닌 쪽은 읽기만 가능.

<br />

## 변경 감지와 병합(merge)

-   준영속 엔티티: 영속성 컨텍스트가 더는 관리하지 않는 엔티티.

### 준영속 엔티티를 수정하는 2가지 방법

-   변경 감지 기능 사용
-   병합 사용

### 변경 감지 기능 사용

-   영속성 컨텍스트에서 엔티티를 다시 조회한 후에 데이터를 수정하는 방법.

1. 트랜잭션 안에서 엔티티를 다시 조회, 변경할 값 선택
2. 트랜잭션 커밋 시점에 변경 감지
3. 데이터베이스에 UPDATE SQL 실행

### 병합시 동작 방식

1. 준영속 엔티티의 식별자 값으로 영속 엔티티 조회
2. 영속 엔티티 값을 준영속 엔티티의 값으로 모두 교체
3. 트랜잭션 커밋 시점에 변경 감지 기능이 동작해서 데이터베이스에 UPDATE SQL 실행

    <br />

## 개념

-   JDBC: Java Database Connectivity: 자바 프로그램이 데이터베이스와 연결되어 데이터를 주고 받을 수 있게 해주는 프로그래밍 인터페이스.

-   HikariCP: DB Connection Pool
-   Hibernate: 자바 언어를 위한 ORM 프레임워크
    <img src = "https://user-images.githubusercontent.com/48986787/130643074-1e9bc19b-c81a-42d4-bfaf-921ef8e4bd9f.png">

-   JPA: 관계형 데이터 베이스를 사용하는 방식을 정의한 인터페이스.
    -   관계형 데이터 베이스와 객체의 패러다임 불일치 문제 해결, 영속성 컨텍스트(엔티티를 영구 저장하는 환경) 제공

<br />

## ManyToMany

-   실무에서 사용하지 말자.
-   @ManyToMany를 사용해도 알아서 중간테이블 만들어주고 매핑되고 문제 없지만, 테이블 매핑에 필요한 정보들 외에 중간 테이블이 가져야할 column 이 생길 수 있음.
-   ex) Member - Order - Item : Order가 발생한 시간 등

<br />

## Lazy loading

ex) findAll() -> query 1
1:N 일 때 각각의 만큼의 객체 조회하는 쿼리 N번 수행

<br />

## Persistence Context

인스턴스로 존재하는 엔티티를 관리하고 영속화시키는 논리적 영역.

-   쉽게 말하자면 DB에 저장.
-   `Persistence Context`에서 `entity`를 관리하고 필요에 따라 DB의 데이터를 저장, 조회, 수정, 삭제
-   이러한 작업을 담당하는 객체를 `Entity Manager`

### 영역

-   `1차 캐시 저장소`: Persistence Context가 관리하는 entity 정보 보관. 아직 DB에 저장된 상태는 아님.
-   `쿼리문 저장소(SQL 저장소)`: JPA는 필요한 쿼리문을 보관. 최대한 여러 쿼리문을 모아두고, DB에 접근하는 횟수를 최소화하여 성능상 이점.
    -   DB에 접근하는 행위는 EntityManager의 `flush()`로 진행

## Reference

-   [[Spring] 스프링 AOP (Spring AOP) 총정리](https://engkimbs.tistory.com/746#:~:text=AOP%EB%8A%94%20Aspect%20Oriented%20Programming,%EC%9C%BC%EB%A1%9C%20%EA%B0%81%EA%B0%81%20%EB%AA%A8%EB%93%88%ED%99%94%ED%95%98%EA%B2%A0%EB%8B%A4%EB%8A%94%20%EA%B2%83%EC%9D%B4%EB%8B%A4.)

-   [[Logging] SLF4J란?](https://livenow14.tistory.com/63)

-   [JPA 연관 관계 한방에 정리(단방향/양방향, 연관 관계의 주인, 일대일, 다대일, 일대다, 다대다)](https://jeong-pro.tistory.com/231)
