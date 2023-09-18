## 용어 정리

- 살충제 페러독스
  - 동일한 테스트 케이스에 의한 반복적 테스트는 새로운 버그를 찾지 못함
- 데이터 마이닝
  - 대량의 데이터 안에서 체계적이고 일정한 규칙이나 패턴을 찾아내는 기술

- 정적 분석 도구
  - pmd, cppcheck, checkstyle, sonarQube 등
  - 소스 코드의 실행 없이, 코드의 의미를 분석해 결함을 찾아낸느 우너시적 코드 분석 기법

- 애플리케이션 성능

  - 처리량(Throughput) : 일정 시간 내 애플리케이션이 처리하는 일의 양
  - 응답 시간(Response Time) : 애플리케이션에 요청을 전달한 시간부터 응답이 도착할 때까지 걸린 시간
  - 경과 시간(Turn Around Time) : 애플리케이션에 작업을 의뢰한 시간부터 처리가 완료될 때까지 걸린 시간
  - 자원 사용률(Resource usage) : 애플리케이션이 의뢰한 작업을 처리하는 동안의 CPU 사용량, 메모리 사용량, 네트워크 사용량 등

- 디자인 패턴

  - https://velog.io/@bonni/%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-%EC%8B%A4%EA%B8%B0-%EB%94%94%EC%9E%90%EC%9D%B8-%ED%8C%A8%ED%84%B4-%EC%A0%95%EB%A6%AC

  - 생성

    - builder : 생성 단계를 캡슐화 해서 구축 공정을 동일하게 이용하도록 하는 패턴

    - Prototype : 기존 객체를 복제해서 새 객체를 생성할 수 있도록 하는 패턴

      등

  - 구조

    - Bridge : 추상과 구현을 분리해서 결합도를 낮춘 패턴

      등

  - 행위
    - Observer : 상태가 변할 때 의존자들에게 알리고 자동으로 업데이트 하는 패턴

- CREATE INDEX

  - ```SQL
    CREATE [UNIQUE] INDEX 인덱스명
    	ON 테이블명(속성명 [ACS|DESC]);
    ```

  - 정렬 여부 (ASC OR DESC) / 생략하면 오름차순으로 정렬

- 웹 서비스 방식
  - SOAP(Simple Object Access Protocol)
    - HTTP, HTTPS, SMPT 등의 프로토콜을 이용하여 XML 기반의 메시지를 교환하는 프로토

- 데이터베이스 설계
  - 순서 : 요구사한 분석 -> 개념적 설계 -> 논리적 설계 -> 물리적 설계 -> 구현
- 즉시갱신 회복 기법
  - Redo, Undo 가 모두 실행, 트랜잭션 수행 중 갱신 결과를 바로 DB에 반영

- 스니핑
  - 직접 공격하지 않고 네트워크 중간에서 남의 패킷의 정보를 몰래 도청하는 공격 기법

- NAT(Network Address Translation) : 사설 ip 주소 -> 공인 ip 주소 변환하는 주소 변환기

- 동치 분할 검사(Equivalence Partitioning)
  - 도메인별로 유효값과 무효값을 그루핑하여 나누어서 검

- unix
  - 계층 구조(트리 구조)의 파일 시스템

- RARP
  - 역순 주소 결정 프로토콜 (Reverse Address Resolution Protocol)
- IPC
  - 프로세스 간 통신

- 데이터 모델 구성 요소
  - 연산
  - 구조
  - 제약 조건

- MAC; Mandatory Access Control)
  - 강제적 접근 통제 (MAC; Mandatory Access Control)
- DAC; Discretionary Access control 
  - 임의적 접근 통제
- RBAC; Role-based Access Control
  - 역할 기반 접근 통제
