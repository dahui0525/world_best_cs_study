# REST API
- REST : Representational State Transfer의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것
- REST(ful) API : REST 원칙을 따르는 API를 의미함. HTTP URI를 통해 자원을 명시하고, HTTP Method를 통해 해당 자원에 대한 상태를 주고 받는 방식

# REST의 특징
1. 균일한 인터페이스  <br>
요청이 어디에서 오는지와 무관하게, 동일한 리소스에 대한 모든 API 요청은 동일하게 보인다. 즉, REST API는 사용자의 이름이나 이메일 주소 등의 동일한 데이터 조각이 오직 하나의 URI에 속함을 보장해야 함. <br>

2. 클라이언트-서버 디커플링.  <br>
REST API 디자인에서 클라이언트와 서버 애플리케이션은 서로 간에 완전히 독립적이어야 함.  <br>
즉, 클라이언트 애플리케이션이 알아야 하는 유일한 정보는 요청된 리소스의 URI이며, 다른 방법으로 서버 애플리케이션과 상호작용할 수 없음.

3. Stateless.  <br>
REST API는 stateless하여 각 요청에서 이의 처리에 필요한 모든 정보를 포함해야 함을 의미함 즉, REST API는 서버측 세션을 필요로 하지 않고 클라이언트 요청과 관련된 데이터를 저장할 수 없음.

4. 캐싱 가능성. <br>
가능하면 리소스를 클라이언트 또는 서버측에서 캐싱할 수 있어야 함. 그래서 서버 응답에는 전달된 리소스에 대해 캐싱이 허용되는지 여부에 대한 정보도 포함되어야 하고, 이의 목적은 서버측의 확장성 증가와 함께 클라이언트측의 성능 향상을 동시에 얻는 것임.

5. 계층 구조 아키텍처. <br>
REST API에서는 호출과 응답이 서로 다른 계층을 통과하는데 이 때 통신 루프에는 다수의 서로 다른 중개자가 있을 수 있음.
REST API는 엔드 애플리케이션 또는 중개자와 통신하는지 여부를 클라이언트나 서버가 알 수 없도록 설계되어야 함을 의미.

# REST의 장단점
- 장점
1. HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없다.
2. HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해 준다.
3. HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
4. Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
5. REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
6. 여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
7. 서버와 클라이언트의 역할을 명확하게 분리한다.

- 단점
1. 표준이 자체가 존재하지 않아 정의가 필요하다.
2. HTTP Method 형태가 제한적이다.
3. 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구된다.
4. 구형 브라우저에서 호환이 되지 않아 지원해주지 못하는 동작이 많다.(익스폴로어)

### 면접 질문
- **Rest 개념에 대해 설명해 보세요.** <br>
REST란 Representational State Transfer의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것을 말합니다. <br>
REST API 에서는 HTTP URI를 통해 자원을 명시하고 HTTP Method를 통해 해당 자원에 대한 상태를 주고 받습니다.
이를 통해 API 메시지가 의도하는 바를 명확하게 나타내므로 요청 사항에 대해 쉽게 파악할 수 있습니다.
