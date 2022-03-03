# 7. 마이크로서비스 쿼리 구현

## 마이크로서비스에서 쿼리작성의 어려움

-   여러 서비스, 여러 DB에 분산된 데이터를 조회해야 하는데, 기존 분산 쿼리 메커니즘은 기술적으로 가능하지만 캡슐화에 위배되기 때문에 사용할 수 없음.

## 마이크로서비스 쿼리 패턴

-   `API 조합(composition) 패턴`: 서비스 클라이언트가 데이터를 가진 여러 서비스를 직접 호출하여 그 결과를 조합하는 패턴. 가장 단순한 방법
-   `CQRS(커맨드 쿼리 책임 분산) 패턴`: 쿼리만 지원하는 하나 이상의 뷰 전용 DB를 유지하는 패턴.

## 목차

-   [7.1 API 조합 패턴 응용 쿼리](https://github.com/oereo/TIL/blob/main/MicroServicePattern/7.%20%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C%EC%84%9C%EB%B9%84%EC%8A%A4%20%EC%BF%BC%EB%A6%AC%20%EA%B5%AC%ED%98%84/7.1_API_%EC%A1%B0%ED%95%A9_%ED%8C%A8%ED%84%B4_%EC%9D%91%EC%9A%A9_%EC%BF%BC%EB%A6%AC.md)

-   [7.2 CQRS 패턴](https://github.com/oereo/TIL/blob/main/MicroServicePattern/7.%20%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C%EC%84%9C%EB%B9%84%EC%8A%A4%20%EC%BF%BC%EB%A6%AC%20%EA%B5%AC%ED%98%84/7.2_CQRS_%ED%8C%A8%ED%84%B4.md)
