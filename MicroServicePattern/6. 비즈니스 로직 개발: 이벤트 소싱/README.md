# 6. 비즈니스 로직 개발: 이벤트 소싱

<b>이벤트 소싱 기법</b>: 이벤트 중심으로 비즈니스 로직을 작성하고 도메인 객체를 저장하는 방법.

<br />

## 왜 사용할까?

-   애그리거트가 생성/수정될 때마다 무조건 이벤트를 발행해서 프로그래밍 오류를 제거할 수 있기 때문에

<br />

## 무엇을 배울까?

-   이벤트 소싱의 작동 원리
-   이벤트 소싱을 이용하여 비즈니스 로직을 작성하는 방법
-   이벤트 저장소에 각 애그리거트를 일련의 이벤트 시퀀스로 저장하는 방법
-   이벤트 소싱의 장단점과 이벤트 저장소의 구현 방법
-   이벤트 소싱 기반의 비즈니스 로직을 간편하게 작성할 수 있는 프레임워크
-   이벤트 소싱이 사가 구현에 좋은 이유

<br />

## 목차

-   [6.1 이벤트 소싱 응용 비즈니스 로직 개발](https://github.com/oereo/TIL/blob/main/MicroServicePattern/6.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EA%B0%9C%EB%B0%9C:%20%EC%9D%B4%EB%B2%A4%ED%8A%B8%20%EC%86%8C%EC%8B%B1/6.1_%EC%9D%B4%EB%B2%A4%ED%8A%B8_%EC%86%8C%EC%8B%B1_%EC%9D%91%EC%9A%A9_%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4_%EB%A1%9C%EC%A7%81_%EA%B0%9C%EB%B0%9C.md)

-   [6.2 이벤트 저장소 구현](https://github.com/oereo/TIL/blob/main/MicroServicePattern/6.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EA%B0%9C%EB%B0%9C:%20%EC%9D%B4%EB%B2%A4%ED%8A%B8%20%EC%86%8C%EC%8B%B1/6.2_%EC%9D%B4%EB%B2%A4%ED%8A%B8_%EC%A0%80%EC%9E%A5%EC%86%8C_%EA%B5%AC%ED%98%84.md)

-   [6.3 사가와 이벤트 소싱을 접목](https://github.com/oereo/TIL/blob/main/MicroServicePattern/6.%20%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4%20%EB%A1%9C%EC%A7%81%20%EA%B0%9C%EB%B0%9C:%20%EC%9D%B4%EB%B2%A4%ED%8A%B8%20%EC%86%8C%EC%8B%B1/6.3_%EC%82%AC%EA%B0%80%EC%99%80_%EC%9D%B4%EB%B2%A4%ED%8A%B8_%EC%86%8C%EC%8B%B1%EC%9D%84_%EC%A0%91%EB%AA%A9.md)
