# craftsmanship

## Table of Contents

- [algorithm](#algorithm)
- [dynamic-programming](#dynamic-programming)
- [Java](#java)
- [Kafka](#kafka)
- [pip](#pip)
- [reactive-programing](#reactive-programing)

## Algorithm

### dynamic programming
- solve sub-problem and apply main-problem (main problem - sub problem - sub sub problem)
- memorization - store and reuse result 
- bottom up
- use array table dp[i] or dp[i][j] for sub-problem

### back tracking
- Define Decision space -> Search -> Back Tracking
- decision space는 모든 경우의 수를 의미 (a|b|c)
- def bt(output, problem, index)
```java //
// for => decision space
// recursive => backtracking
backtracking(candidates, decisionSpace, start) {
    for(int i = start; i< candidates.length; i++) {
        // return result

        // avoid duplicate decison space
        if (i != start && candidates[i] == candidates[i - 1]) { continue; }
        
        decisionSpace.add(candidates[i]);
        backtracking(candidates, decisionSpace, i++);
        decisionSpace.remove(lastIndex);
    }
}
```

### binary search
```
 public boolean binarySearch(int[] matrix, int s, int e, int target) {
        while (s <= e) {
            int mid = s + (e - s) / 2;

            if (matrix[mid] == target) return true;
            else if (target < matrix[mid]) e = mid - 1;
            else s = mid + 1;
        }

        return false;
    }
```


## Java
    - Stream processing : 스트림이란 한 번에 한 개씩 만들어지는 연속적인 데이터 항목들의 모임
    - Stream API가 조립라인처럼 어떤 항목을 연속적으로 제공하는 어떤 기능이라고 단순하게 생각
    - Behavior parameterization(동작 파라미터화) : 메서드를 다른 메서드의 인수로 넘겨주는 기능을 제공
        - 메서드 내부적으로 다양한 동작을 수행할 수 있도록 코드를 메서드 인수로 전달
        - 아직은 어떻게 실행할 것인지 결정하지 않은 코드 블록을 의미. 코드 블ㄹ록에 따라 메서드의 동작이 파라미터화 됨
    - 함수형 프로그래밍 패러다임의 핵심적인 사항
        - no shared mutable data (공유되지 않은 가변 데이터)
        - 메서드와 함수 코드를 다른 메서드로 전달
    - Default method : 구현 클래스에서 구현하지 않아도 되는 메서드를 인터페이스가 포함할 수 있는 기능. 메서드 바디는 클래스 구현이 아니라 인터페이스의 일부로 포함된다
    - 람다 표현식 : 메서드로 전달할 수 있는 익명 함수를 단순화한 것
        - 람다 표현식에는 return이 함축되어 있으므로 return 문을 명시적으로 사용하지 않아도 됨
    - 함수형 프로그래밍
        - 메서드와 람다를 일급값으로 사용하는것
        - 가변 공유 상태가 없는 병렬 실행
    - Optional<T> : 값을 갖거나 갖지 않을 수 있는 컨테이너 객체
    - 함수형 인터페이스 : 디폴트 메서드가 있더라도 추상 메서드가 오직 하나인 인터페이스
        - @FunctionalInterface

    - StringBuilder, StringBuffer
        - String은 불변이라 덧셈 연산자를 이용해 String 인스턴스의 문자열을 결합하면, 내용이 합쳐진 새로운 String 인스턴스를 생성하게 되어, 문자열을 많이 결합할수록 공간의 낭비뿐만 아니라 속도 또한 매우 느려지게 된다는 단점이 있다
        - StringBuffer/StringBuilder 클래스는 문자열 연산 등으로 기존 객체의 공간이 부족하게 되는 경우, 기존의 버퍼 크기를 늘리면 유연하게 동작합니다.
        - StringBuffer는 각 메서드별로 Synchronized Keyword가 존재하여, 멀티스레드 환경에서도 동기화를 지원하고 StringBuilder는 동기화를 보장하지 않음.

    - sort
        - compare (o1, o2)가 음수를 리턴하면 o1이 o2보다 왼쪽에 위치한다.
        - compare (o1, o2)가 양수를 리턴하면 o1이 o2보다 오른쪽에 위치한다.
    ```
    List<String> words
    words.sort(new Comparator<String>() {
        @Override
        public int compare(String o1, String o2) {
            if (o1.length() == o2.length()) return 0;
            return o1.length() > o2.length() ? -1 : 1;
        }
    });
    ```



        


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


## 프로세스 vs 스레드
- 프로세스는 운영체제부터 자원을 할당받는 작업 단위
스레드는 프로세스가 할당받은 자원을 이용하는 실행 단위
하나의 프로세스가 생성되면 하나의 프로세스가 같이 생성되며 이를 메인스레드라고 한다.
프로세스는 자신만의 고유 공간과 자원을 할당 받아 사용하지만 스레드는 다른 스레드와 한 프로세스 내에 주소공간이나 자원들을 공유하며 실행 된다.
이 때문에 멀티 프로세스를 이용하여 처리하던 일을 멀티 스레드로 구현하면 프로세스를 생성하여 1)자원을 할당 하는 시스템 콜이 줄어들게 되며 2)프로세스 간의 통신보다 스레드 간의 통신 비용이 적어 공간과 자원 소모가 훨씬 줄어든다.

## reactive-programing
- 데이터의 흐름을 먼저 정의하고 데이터가 변경되었을 때 연관된 작업이 실행
- WebFlux는 쉽게 쓰기 위해 Reactive Streams 라이브러리를 기반으로 만들어진 구현체
    - WebFlux -> Reactive Streams가 적용된 stream (비동기 단일스레드 동작)
    - Servlet MVC -> Reactive Streams가 적용된 stream (멀티 스레디 방식)
- 비동기로 처리 가능하며 변경이 일어나면 이벤트 기반으로 프로그램을 구성하기 위한 라이브러리
