# 인증방식

## API Key

사용자나 애플리케이션을 식별하는 간단한 인증 방식

### 동작 방식

1. 사용자는 API Key를 발급받는다. (발급 받는 과정은 서비스들마다 다르다. 예를들어 공공기관 API같은 경우에는 신청에 필요한 양식을 제출하면 관리자가 확인 후 Key를 발급해준다.
2. 해당 API를 사용하기위해 Key와 함께 요청을 보낸다.
3. Application은 요청이 오면 Key를 통해 User정보를 확인하여 누구의 Key 인지 권한이 무엇인지를 확인한다.
4. 해당 Key의 인증과 인가에 따라 데이터를 사용자에게 반환한다.

### 단점

- Key가 유출된 경우 누구나 그 키를 사용할 수 있어 보안이 낮다.
- 따라서 주기적으로 Key를 업데이트 해야 하는 데 한쪽만 업데이트가 된다거나 하는 상황이 발생할 수 있다.

## OAuth2

타사의 어플리케이션이 사용자를 대신해 서비스를 이용할 수 있는 권한을 부여하는 인증 방식이다.

사용자의 로그인 정보를 타사와 서비스가 공유하지 않아도 해당 앱이나 웹사이트가 사용자의 대신에 특정 작업을 허용하도록 수행하도록 허용한다.

### OAuth 1과 달라진 점

OAuth1 : 요청에 서명을 포함하는 방식 ( HMAC-SHA1 알고리즘 사용하여 서명 생성)

OAuth2 : SSL/TLS 를 통한 HTTPS 통신을 통해 보안을 제공 , api서버에서 인증 서버와 리소스 서버가 분리도 함 , 다양한 인증 방식 제공

**인증 서버**

인증 서버는 클라이언트(사용자나 서비스)의 인증을 담당하고, 유효한 인증 후에는 액세스 토큰이나 리프레시 토큰과 같은 자격 증명을 발급

**리소스 서버**

리소스 서버는 보호된 사용자 데이터(예: 사용자 프로필 정보, 사진, 소셜 미디어 게시물 등)를 호스팅하고 관리

인증 서버에 의해 발급된 액세스 토큰을 받아서 요청을 인증하고, 유효한 요청에 한해 데이터에 접근을 허용

### 인증 종류

1. Authorization Code Grant
   1. 가장 일반적으로 사용되는 OAuth 2.0 인증 방식
   2. 밑의 사진 과정
2. Implicit Grant
   1. **Implicit Grant**는 특히 자바스크립트와 같이 퍼블릭 클라이언트에서 사용
   2. authorization code 단계 없이 바로 **`access token`**을 클라이언트에 제공
   3. 보안상의 이유로 권장 X
3. Password Credentials Grant
   1. 사용자의 유저네임과 패스워드를 직접 클라이언트에 제공하고, 클라이언트가 이 정보를 사용해 인증 서버로부터 **`access token`**을 요청하는 방식
   2. \*\*\*\*사용자의 신뢰를 얻고 있는 클라이언트에서만 사용, 보안 상의 이유로 권장 X
4. Client Credentails Grant
   1. 클라이언트 자체의 인증에 사용
   2. 클라이언트가 사용자 대신 자신의 자격을 사용하여 **`access token`**을 요청할 때 사용, 서버 간 API 통신에 적합

### 프로세스

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e3e78d12-2dc1-4f0e-b156-d02e7bb67166/9f5a363b-8d74-41ee-9aec-032370dc343c/Untitled.png)

### 문제점

- 기존 API Key방식에 비해 좀 더 복잡한 구조를 가진다.
- 통신에 사용하는 Token은 무의미한 문자열을 가지고, 이 문자열 자체에는 사용자나 권한에 대한 정보가 내포되어 있지 않습니다. 따라서 토큰의 진위를 확인하기 위해서는 추가적인 검증 절차가 필요합니다.

## JWT

JWT는 JSON Web Token의 줄임말로 인증 흐름의 규약이 아닌 Token 작성에 대한 규약이다. 기본적인 Access Token은 의미가 없는 문자열로 이루어져 있어 Token의 진위나 유효성을 매번 확인해야 하는 것임에 반하여, JWT는 인증여부 확인을 위한 값, 유효성 검증을 위한 값 그리고 인증 정보 자체를 담고 있기 때문에 인증서버에 묻지 않고도 사용할 수 있다.

이러한 특성 때문에 JWT는 분산된 서비스나 마이크로서비스 아키텍처에서 인증을 관리하기에 특히 유용한 방식으로 평가받습니다

### 문제점

서버에 직접 연결하여 인증을 학인하지 않아도 되기 때문에 생기는 장점들이 많다. 하지만 토큰 자체가 인증 정보를 가지고 있기 때문에 민감한 정보는 토큰에 포함시키지 않고 필요 시 인증 서버에 다시 접속하여 확인하는 과정이 필요합니다.

### 면접 질문

1. 인증 방식에 대해서 아는 대로 설명해주세요

인증은 사용자나 시스템이 자신이 주장하는 대로 실제로 그러한지를 확인하는 프로세스입니다.
인증 방식에는 API Key, OAuth, JWT 등이 있습니다.

API Key 방식은 가장 간단한 형태의 인증으로, 사용자나 애플리케이션이 서비스에 접근할 때 사용하는 고유한 키를 제공합니다. 이 키는 요청과 함께 서버로 전송되어 사용자 또는 클라이언트의 신원을 확인하는 데 사용됩니다. API Key는 구현이 쉽지만, 키가 노출될 경우 보안에 취약할 수 있습니다.

OAuth는 타사 애플리케이션이 사용자의 계정에 제한된 접근을 허용할 때 주로 사용됩니다. OAuth 2.0은 이를 위한 현대적인 표준으로, 보다 유연하고 확장성이 높은 인증 옵션을 제공합니다. 이는 인증 서버가 사용자를 대신해 토큰을 발급하고, 이 토큰을 사용해 리소스 서버에 접근하게 합니다.

JWT (JSON Web Tokens)는 디지털 서명된 토큰을 사용하여 두 서버나 애플리케이션 간에 안전하게 정보를 전송할 수 있는 방식입니다. JWT는 인증 정보뿐만 아니라 추가 데이터도 포함할 수 있어, 서버가 추가적인 데이터베이스 조회 없이도 사용자의 신원을 확인하고 권한을 부여할 수 있습니다.