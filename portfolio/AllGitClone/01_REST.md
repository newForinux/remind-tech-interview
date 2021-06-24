## 🤔 REST, RESTful이란 무엇인가요?

### REST의 의미

REST는 Representational State Transfer의 약자로, 리소스를 <strong>이름으로 구분하여</strong> 해당 리소스의 <strong>정보(State)</strong>를 주고받는 모든 것을 의미합니다.

자원의 표현(representation)에 의한 상태(state) 전달(transfer)을 말하며, 주로 JSON, XML 형식으로 주고받는 것이 일반적입니다.

<strong>RESTful</strong>하다는 것은 REST 구조 스타일과 원칙을 모두 만족한다는 것입니다.

즉, REST라는 구조 스타일과 구조 설계 원칙을 모두 적용한 API / 웹 서비스를 RESTful API / 웹 서비스라고 합니다.

<br>

리소스를 다루는 가장 대표적인 방법은 <strong>CRUD (Create, Read, Update, Delete)</strong> 연산으로,

RESTful에서는 각각 POST, GET, PUT/POST, DELETE와 같은 HTTP 메소드로 정의합니다.


<br>

### REST의 특징

- <b>서버-클라이언트 구조</b> : REST 서버가 API를 제공하고 비즈니스 로직을 처리합니다. 클라이언트는 context (세션 등)을 관리하고 책임집니다. 서로간 의존성이 줄어드는 설계입니다.


- <b>Stateless</b> : HTTP 프로토콜과 마찬가지로 무상태성입니다. 서버는 클라이언트의 context 정보를 완전히 신경쓰지 않고, 클라이언트의 요청만을 처리합니다. 서비스의 자유도가 높아집니다.


- <b>Cacheable</b> : HTTP의 강력한 캐싱 기능을 적용할 수 있습니다. 전체적인 응답시간, 성능을 향상시킬 수 있습니다.

- <b>Layered System</b> : 클라이언트는 API 서버만 호출하며, 서버는 비즈니스 로직을 수행합니다. 서버는 여러 계층으로 이루어질 수 있습니다. (보안, load balancing, etc.) 또한, 프록시와 같은 미들웨어를 사용할 수 있습니다.

- <b>Uniform Interface</b> : 리소스에 대한 상태 변경, 조작을 인터페이스에 한정해 수행합니다.

<br><br>

정리하자면, REST는 HTTP URI (Uniform Resource Identifier, 하위 개념으로 URL, URN이 있음)를 통해 리소스를 명시하고,

HTTP 메소드를 통해 해당 자원에 대한 CRUD 연산을 적용해 리소스의 상태 변경을 추구하는 아키텍쳐 스타일인 것입니다.

표준 HTTP 프로토콜을 그대로 사용할 수 있어 범용성이 크고 (다양한 브라우저, 웹과 모바일 디바이스 등 멀티 플랫폼), 별도의 인프라를 구축할 필요가 없습니다.

단점으로는 HTTP 메소드가 제한적이고 구형 브라우저의 호환성 문제가 있습니다.
