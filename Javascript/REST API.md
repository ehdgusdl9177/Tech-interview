## Rest(REpresentational State Transfer)
- HTTP URI를 통해 자원을 명시하고, HTTP Method를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 말한다.
- 웹에서 사용하는 모든 자원을 HTTP URL로 정의하고, HTTP Method를 통해 요청과 응답을 정의하는 방식을 말한다.
- REST는 자원(Resource), 행위(Verb), 표현(Representaions)으로 구성된 API 아키텍쳐이다. 웹의 장점과 HTTP의 우수성을 적극 활용할 수 있는 아키텍쳐로 URI를 통해서 자원을 명시하고 POST, GET, PUT, PATCH, DELETE 등의 Method를 통해서 해당 자원의 CRUD 연산을 적용하는 것을 의미한다. 코드의 재사용성을 높일 수 있으며 프론트엔드와 백엔드의 완전한 분업이 가능해진다.
- REST의 요소
<img width="302" alt="스크린샷 2022-01-02 오후 7 55 01" src="https://user-images.githubusercontent.com/75515697/147873552-33c4fbd4-0ad1-4271-b77a-1da60571d534.png">
- idempotent: 한 번 수행하나, 여러 번 수행했을 때 결과가 같나?

- Resource
  - http://myweb/users 와 같은 URI
  - 모든 것을 Resource(명사)로 표현하고, 세부 Resource에는 id를 붙인다.

- Message
  - 메세지 포맷이 존재: JSON, XML 과 같은 형태가 있다(최근에는 JSON을 씀)
<img width="681" alt="스크린샷 2022-01-02 오후 7 57 33" src="https://user-images.githubusercontent.com/75515697/147873594-58798faf-bc8d-4ca4-9801-e6f007a4f57b.png">

### REST 특징
- Uniform Interface
  - HTTP 표준만 맞는다면, 어떤 기술도 가능한 Interface 스타일
    - 예) REST API 정의를 HTTP + JSON로 하였다면, C, Java, Python, IOS 플랫폼 등 특정 언어나 기술에 종속 받지 않고, 모든 플랫폼에 사용이 가능한 Loosely Couling 구조
  - 포함
    - Self-Descriptive Messages
      - API 메시지만 보고, API를 이해할 수 있는 구조(Resource, Method를 이용해 무슨 행위를 하는지 직관적으로 이해할 수 있다)
    - HATEOAS(Hypermedai As The Engine Of Application State)
      - Application의 상태(state)는 Hyperlink를 통해 전이되어야 한다.
      - 서버는 현재 이용 가능한 다른 작업에 대한 하이퍼링크를 포함하여 응답해야한다.
    - Resource Identification In Requests
    - Resource Manipulation Through Representations

- Statelessness
  - 즉, HTTP Session과 같은 컨텍스트 저장소에 상태 정보 저장 안함
  - Request만 Message로 처리하면 되고, 컨텍스트 정보를 신경쓰지 않아도 되므로, 구현이 단순해진다.
  - 따라서, REST API 실행중 실패가 발생한 경우, Transaction 복구를 위해 기존의 상태를 저장할 필요가 있다.(POST Method 제외)

- Resource 지향 아키텍쳐(ROA: Resource Oriented Architecture)
  - Resource 기반의 복수형 명사 형태의 정의를 권장

- Client-Server Architecture
- Cache Ability
- Layered System
- Code On Demand(Optional)
