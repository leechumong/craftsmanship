# craftsmanship

## Table of Contents

- [algorithm](#algorithm)
- [dynamic-programming](#dynamic-programming)
- [Java](#java)
- [Kafka](#kafka)
- [pip](#pip)

## algorithm

### dynamic programming
- solve sub-problem
- store and reuse result
- bottom up

## Java
    - Stream processing : 스트림이란 한 번에 한 개씩 만들어지는 연속적인 데이터 항목들의 모임
    - Stream API가 조립라인처럼 어떤 항목을 연속적으로 제공하는 어떤 기능이라고 단순하게 생각
    - Behavior parameterization(동작 파라미터화) : 메서드를 다른 메서드의 인수로 넘겨주는 기능을 제공
    - 함수형 프로그래밍 패러다임의 핵심적인 사항
        - no shared mutable data (공유되지 않은 가변 데이터)
        - 메서드와 함수 코드를 다른 메서드로 전달

## Kafka
- Distributed streaming platform
    - Description:
        - Real-time data pipelines
        - Publish and subscribe to streams of records.
        - A topic is a category or feed name to which records are published.
        - For each topic, the Kafka cluster maintains a partitioned log
    - Refercences
        - https://kafka.apache.org/intro

## pip
- pip는 파이썬으로 작성된 패키지 소프트웨어를 설치 · 관리하는 패키지 관리 시스템 이다. 
- pip install docker-compose


## Cluster
- 다른 서버들을 하나로 묶어 하나의 시스템 같이 동작하게 함.
- 시스템에 장애가 발생하면, 서비스가 다른 정상적인 서버에서 동작하며 클라이언트에게 지속적이고 끊임없이 고가용성의 서비스를 제공할 수 있다.

