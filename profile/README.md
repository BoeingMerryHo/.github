# OingLogistics

[커버 이미지]

[프로젝트 간단 소개]

## :walking: 프로젝트 소개

### 서비스 목표


### 기술적 목표




## :memo: 개발 노션 및 산출물

[프로젝트 설계 및 구현 산출물](https://github.com/BoeingMerryHo/kbo-ticketing-platform/wiki)

## :construction_worker: 팀원 역할 분담

| 김기훈 | 이예본 | 이지언 | 이하은 | 전은배 |
|--------|--------|--------|--------|--------|
| ![김기훈](https://github.com/user-attachments/assets/84fb1bd5-32f5-4cce-bc65-3f6daf89c144) | ![이예본](https://github.com/user-attachments/assets/24347135-3c55-409f-af30-81bf898b2c6e) | ![이지언(팀장)](https://github.com/user-attachments/assets/bf8f40c5-89ea-4945-a3eb-c690fb62c145) | ![이하은](https://github.com/user-attachments/assets/220ea7de-5ba8-4d4c-841b-cac92aa5a648) | ![전은배](https://github.com/user-attachments/assets/e418f56b-5e91-4046-9f79-a6482f0237e7)
| (한 것) | (한 것) | (한 것) | (한 것) | (한 것) |
| [GitHub](https://github.com/oneul0) | [GitHub](https://github.com/ybon1107) | [GitHub](https://github.com/Leejieon) | [GitHub](https://github.com/haisley77) | [GitHub](https://github.com/Juneunbae) |


## :calendar: 개발 기간

2025.04.03 - 2025.05.01 (4주)

## :hammer_and_wrench: 사용 기술

### 🛠 버전


| 분류               | 상세                                      |
|--------------------|-------------------------------------------|
| **IDE**            | IntelliJ IDEA                             |
| **Language**       | Java 17                                   |
| **Framework**      | Spring Boot 3.4.3                         |
| **Build Tool**     | Gradle 8.1                                |
| **Database**       | PostgreSQL 17                             |
| **In-Memory DB**   | Redis                                     |
| **Local Cache**    | Caffeine                                  |
| **Message Queue**  | RabbitMQ                                  |
| **API 통신**       | REST API, FeignClient                     |
| **컨테이너화**     | Docker                                    |


### 🛠 주요 기술 스택

| 분류               | 상세                                      |
|--------------------|-------------------------------------------|
| **Backend**            | <img src="https://img.shields.io/badge/java-007396?style=flat-square&logo=java&logoColor=white"/> <img src="https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=SpringBoot&logoColor=white"/> <img src="https://img.shields.io/badge/SpringSecurity-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white"/>                           |
| **Database**       | <img src="https://img.shields.io/badge/postgresql-4169E1?style=flat-square&logo=postgresql&logoColor=white"/> <img src="https://img.shields.io/badge/redis-FF4438?style=flat-square&logo=redis&logoColor=white">                                  |
| **Version & Issue**      | <img src="https://img.shields.io/badge/git-F05032?style=flat-square&logo=git&logoColor=white"> <img src="https://img.shields.io/badge/github-181717?style=flat-square&logo=github&logoColor=white"> <img src="https://img.shields.io/badge/notion-000000?style=flat-square&logo=notion&logoColor=white">                       |
| **Infra**     | <img src="https://img.shields.io/badge/docker-2496ED?style=flat-square&logo=docker&logoColor=white">                              |



## :building_construction: 아키텍처

![Image](https://github.com/user-attachments/assets/fe26d45d-a856-4ee3-a670-9c4f9814ce41)

## :memo: ERD

![Image](https://github.com/user-attachments/assets/5d41c648-9bf0-4d0c-8e56-6109679b2122)


## :movie_camera: 기능

### :memo: 시퀀스 다이어그램

![Image](https://github.com/user-attachments/assets/faeb0ffd-998b-4249-947a-7607930f91f2)

### :desktop_computer: 프로젝트 주요 기능

<details>
<summary>업체 (company-service)</summary>

 ### Company (업체 관리)

- **CompanyAdminController (/admin/v1/companies)**
    - 새로운 업체 생성
    - 업체 목록 전체 조회
    - 특정 업체 상세 조회
    - 특정 업체 정보 수정
    - 특정 업체 삭제
- **CompanyController (/api/v1/companies)**
    - 새로운 업체 생성
    - 업체 목록 전체 조회
    - 특정 업체 상세 조회
    - 특정 업체 정보 수정
    - 특정 업체 삭제
- **CompanyFeignClientController (/company-service/companies)**
    - 특정 업체 상세 조회
      
</details>
<details>
<summary>배송 (delivery-service)</summary>

 ### Delivery (배송 관리)

- **DeliveryAdminController (/admin/v1/deliveries)**
    - 새로운 배송 생성 (테스트 용도, 메시지큐 도입으로 사용 중단)
    - 특정 배송 정보 수정
    - 특정 배송 상태 수정
    - 특정 배송 삭제
    - 특정 배송 상세 조회
    - 배송 목록 전체 조회
    - 특정 배송 경로 상세 조회
    - 특정 배송의 경로 목록 조회
    - 특정 배송 경로 상태 수정
- **DeliveryController (/api/v1/deliveries)**
    - 특정 배송 정보 수정
    - 특정 배송 상태 수정
    - 특정 배송 삭제
    - 특정 배송 상세 조회
    - 배송 목록 전체 조회
    - 특정 배송 경로 상세 조회
    - 특정 배송의 경로 목록 조회
    - 특정 배송 경로 상태 수정
- **DeliveryManagerController (/api/v1/deliveries/managers)**
    - 특정 배송 담당자 상세 조회
    - 특정 배송 담당자 전체 조회
- **DeliveryManagerAdminController (/admin/v1/deliveries/managers)**
    - 특정 배송 담당자 상세 조회
    - 특정 배송 담당자 전체 조회
      
</details>
<details>
<summary>허브 (hub-service)</summary>

 ### Hub (허브 관리)

- **HubAdminController (/admin/v1/hubs)**
    - 특정 허브 상세 조회
    - 허브 목록 전체 조회
    - 새로운 허브 생성
    - 특정 허브 정보 수정
    - 특정 허브 삭제
- **HubController (/api/v1/hubs)**
    - 허브 목록 전체 조회
    - 특정 허브 상세 조회
- **HubFeignClientController (/hub-service)**
    - managerId로 허브 정보 조회
    - 최적의 허브 경로 조회
    - 특정 허브 상세 조회
- **HubRouteAdminController (/admin/v1/hub-routes)**
    - 새로운 허브 경로 생성
    - 특정 허브 경로 상세 조회
    - 허브 경로 목록 전체 조회
    - 특정 허브 경로 정보 수정
    - 특정 허브 경로 삭제
      
</details>
<details>
<summary>주문 (order-service)</summary>

 ### Order (주문 관리)

- **OrderAdminController (/admin/v1/orders)**
    - 주문 목록 전체 조회
    - 새로운 주문 생성
    - 특정 주문 상세 조회
    - 특정 주문 정보 수정
    - 특정 주문 삭제
    - 특정 주문의 상세 주문 삭제
- **OrderController (/api/v1/orders)**
    - 주문 목록 전체 조회
    - 특정 주문 상세 조회
    - 새로운 주문 생성
    - 특정 주문 정보 수정
    - 특정 주문 삭제
    - 특정 주문의 상세 주문 삭제
- **OrderFeignClientController (/order-service/orders)**
    - 특정 주문 조회
      
</details>
<details>
<summary>상품 (product-service)</summary>

 ### Product (상품 관리)

- **ProductAdminController (/admin/v1/products)**
    - 새로운 상품 등록
    - 상품 목록 전체 조회
    - 특정 상품 상세 조회
    - 특정 상품 정보 수정
    - 특정 상품 삭제
- **ProductController (/api/v1/products)**
    - 새로운 상품 등록
    - 상품 목록 전체 조회
    - 특정 상품 상세 조회
    - 특정 상품 정보 수정
    - 특정 상품 삭제
- **ProductFeignClientController (/product-service/products)**
    - 특정 상품 상세 조회
      
</details>
<details>
<summary>알림 (slack-service)</summary>

 ### Slack (슬랙 메시지 관리)

- **SlackAdminController (/admin/v1/slack-messages)**
    - 슬랙 메시지 목록 전체 조회
    - 특정 슬랙 메시지 상세 조회
    - 새로운 슬랙 메시지 생성
    - 특정 슬랙 메시지 수정
    - 특정 슬랙 메시지 삭제
- **SlackController (/api/v1/slack-messages)**
    - 새로운 슬랙 메시지 생성 (발송)
      
</details>
<details>
<summary>사용자 (user-service)</summary>

 ### User (사용자 관리)

- **UserAdminController (/admin/v1/users)**
    - 사용자 회원가입
    - 사용자 로그인
    - 사용자 로그아웃
    - 새로운 사용자 생성
    - 특정 사용자 조회
    - 사용자 목록 전체 조회
    - 특정 사용자 정보 수정
    - 특정 사용자에게 권한 부여
    - 특정 사용자 권한 업데이트
    - 특정 사용자 권한 삭제
    - 특정 사용자 삭제
    - 슬랙 인증 코드 요청
    - 슬랙 인증 코드 확인
- **UserController (/api/v1/users)**
    - 사용자 회원가입
    - 사용자 로그인
    - 사용자 로그아웃
    - 특정 사용자 조회
    - 슬랙 인증 코드 요청
    - 슬랙 인증 코드 확인
- **UserFeignClientController (/user-service/users)**
    - 역할별 사용자 목록 조회
    - 배송 서비스 요청으로 역할별 사용자 맵 조회
    - 사용자 ID로 역할 조회
    - 사용자 ID로 슬랙 ID 조회
    - 사용자 ID로 사용자 이름 조회
      
</details>

## :computer: 트러블슈팅

1. [Multi‐Stage Build 를 적용한 도커 이미지 경량화](https://github.com/5ingMaryho/OingLogistics/wiki/%F0%9F%90%B3Multi%E2%80%90Stage-Build-%EB%A5%BC-%EC%A0%81%EC%9A%A9%ED%95%9C-%EB%8F%84%EC%BB%A4-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EA%B2%BD%EB%9F%89%ED%99%94)

2. [Interceptor와 Annotation을 활용한 각 서비스 API 별 권한 검증](https://github.com/5ingMaryho/OingLogistics/wiki/%F0%9F%91%A5Interceptor%EC%99%80-Annotation%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EA%B0%81-%EC%84%9C%EB%B9%84%EC%8A%A4-API-%EB%B3%84-%EA%B6%8C%ED%95%9C-%EA%B2%80%EC%A6%9D)

3. [멀티 모듈 구조 적용](https://github.com/5ingMaryho/OingLogistics/wiki/%F0%9F%A7%A9%EB%A9%80%ED%8B%B0-%EB%AA%A8%EB%93%88-%EA%B5%AC%EC%A1%B0-%EC%A0%81%EC%9A%A9)

4. [동시성 제어와 이벤트 리스너 트랜잭션 관리](https://github.com/5ingMaryho/OingLogistics/wiki/%EB%8F%99%EC%8B%9C%EC%84%B1-%EC%A0%9C%EC%96%B4%EC%99%80-%EB%B6%84%EC%82%B0%EB%9D%BD,-%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EB%B6%84%EB%A6%AC)

## :package: 프로젝트 구동 방법

### 1. Project 소스 코드를 Clone 합니다.

```
git clone https://github.com/5ingMaryho/OingLogistics.git
```

### 2. /OingLogistics/eureka-service/src/main/resources 경로로 이동 후, application.yml 파일을 생성합니다.

```
spring:
  config:
    import:
      - classpath:./application-prod.yml
  profiles:
    group:
      prod: prod
    active: prod
  application:
    name: eureka-service

---
spring:
  config.activate.on-profile: prod

```

### 3. /OingLogistics/eureka-service/src/main/resources 경로로 이동 후, application-prod.yml 파일을 생성합니다.

```
server:
  port: 8761

spring:
  application:
    name: eureka-service


eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
    service-url:
      defaultZone: http://localhost:8761/eureka/
  instance:
    hostname: eureka-service
```


### 4. /OingLogistics/config-service/src/main/resources 경로로 이동 후, application.yml 파일을 생성합니다.

+ key는 현재 비공개입니다. 필요 시 제공하겠습니다.

```
server:
  port: 8888

spring:
  application:
    name: config-service

  profiles:
    active: git

  cloud:
    config:
      server:
        git:
          uri: https://github.com/5ingMaryho/Config.git
          clone-on-start: true
          username: {owner_username}
          password: {owner_password}
```

### 5. /OingLogistics/gateway-service/src/main/resources 경로로 이동 후, application.yml 파일을 생성합니다.

```
spring:
  config:
    import: "optional:configserver:http://localhost:8888/"
  profiles:
    active: prod
  application:
    name: gateway-service
```

### 6. /OingLogistics 경로에서 docker-compose.yml 파일을 실행합니다.

+ 초기 빌드 시 시간이 소요될 수 있습니다.

```
docker compose up -d
```


## :memo: 프로젝트 회고

### 프로젝트 개선점 및 고도화 계획
- 주문 - 상품 동시성 제어
- 분산 환경에서의 데이터 정합성과 부하를 최소화하는 방안을 탐색

### 협업 시 우리 팀이 잘한 점
- 문제나 궁금한 점을 바로 공유하고 함께 해결 방법을 고민하며 함께 성장하는 팀 분위기를 만들었습니다.
- PR 규칙을 정하고 알고 있는 내용, 배운 내용, 고민사항, 설계를 적극적으로 공유하여 팀 전체의 개발 역량을 향상시켰습니다.

### 협업 시 아쉽거나 부족했던 부분들
- 트러블 슈팅 기록과 오류 정리를 체계화해 유사한 문제가 발생했을 때 원인 파악과 해결 시간을 단축하고자 합니다.
- API 구현 및 새로운 기술에 대한 러닝커브로 예상보다 많은 시간이 소요되어 테스트 코드 작성이나 개발 진행이 지연되었습니다. 깃허브 이슈 관리를 통해, 이런 상황을 최소화하고자 노력했습니다.

