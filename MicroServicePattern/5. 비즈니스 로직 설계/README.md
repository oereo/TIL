# 5. 비즈니스 로직 설계

## 도입부

### 마이크로서비스 아키텍처에서의 비즈니스 로직

복잡한 비즈니스 로직을 개발하기 까다로움

-   도메인 모델은 대부분 상호 연관된 클래스가 거미줄처럼 뒤얽혀 있음.
    -   서비스 경계를 넘나드는 객체 레퍼런스를 제거해야 함.
-   마이크로서비스 아키텍처 특유의 트랜잭션 관리 제약 조건하에서도 작동되는 비즈니스 로직 설계
    -   여러 서비스에 걸쳐 데이터 일관성을 유지하려면 `사가 패턴`을 적용해야 함.

### 해결방안

-   서비스 비즈니스 로직을 여러 애그리거트로 구성하는 DDD 애그리거트(aggregate) 패턴으로 해결.
-   애그리거트(aggregate): 한 단위로 취급 가능한 객체를 모아 놓은 것.

### 애그리거트

-   애그리거트를 사용하면 객체 레퍼런스가 서비스 경계를 넘나들 일이 없음.
    -   객체 참조 대신 기본키(pk)를 이용하여 참조.
-   한 트랜잭션으로 하나의 애그리거트만 생성/수정.

## 목차

-   [5.1 비즈니스 로직 구성 패턴](https://github.com/oereo/TIL/blob/main/MicroServicePattern/5.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EC%84%A4%EA%B3%84/5.1_%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4_%EB%A1%9C%EC%A7%81_%EA%B5%AC%EC%84%B1_%ED%8C%A8%ED%84%B4.md)

-   [5.2 도메인 모델 설계: DDD 애그리거트 패턴](https://github.com/oereo/TIL/blob/main/MicroServicePattern/5.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EC%84%A4%EA%B3%84/5.2_%EB%8F%84%EB%A9%94%EC%9D%B8_%EB%AA%A8%EB%8D%B8_%EC%84%A4%EA%B3%84:_DDD_%EC%95%A0%EA%B7%B8%EB%A6%AC%EA%B1%B0%ED%8A%B8_%ED%8C%A8%ED%84%B4.md)

-   [5.3 도메인 이벤트 발행](https://github.com/oereo/TIL/blob/main/MicroServicePattern/5.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EC%84%A4%EA%B3%84/5.3_%EB%8F%84%EB%A9%94%EC%9D%B8_%EC%9D%B4%EB%B2%A4%ED%8A%B8_%EB%B0%9C%ED%96%89.md)

-   [5.4 주방 서비스 비즈니스 로직](https://github.com/oereo/TIL/blob/main/MicroServicePattern/5.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EC%84%A4%EA%B3%84/5.4_%EC%A3%BC%EB%B0%A9_%EC%84%9C%EB%B9%84%EC%8A%A4_%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4_%EB%A1%9C%EC%A7%81.md)

-   [5.5 주문 서비스 비즈니스 로직](https://github.com/oereo/TIL/blob/main/MicroServicePattern/5.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EC%84%A4%EA%B3%84/5.5_%EC%A3%BC%EB%AC%B8_%EC%84%9C%EB%B9%84%EC%8A%A4_%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4_%EB%A1%9C%EC%A7%81.md)
