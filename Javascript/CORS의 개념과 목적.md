## CORS
- Cross-Origin-Sharing은 추가적인 HTTP header를 사용해서 실행중인 웹이 다른 origin의 리소스에 접근할 수 있도록 하는 메커니즘을 의미한다.

### 필요한 이유
- 기본적으로 브라우저는 Same-origin policy 동일 출처 정책을 따른다.
- 따라서 API 요청시 이 정책에 따라 동일한 출처의 리소스만을 요청할 수 있다.
- 하지만 웹 어플리케이션을 구현하다보면, 다른 출처에 있는 리소스를 요청해야하는 경우가 많다.
- 이를 안전하게 처리할 정책 => cross-origin 요청을 제한적으로 허용한다.

### 어떻게 구성되고 동작하는가
- 브라우저는 출처가 다른 요청을 보낼때 Access-Control-Allow-Origin이라는 헤더를 추가한다.
- 만약 리소스에도 동일한 Access-Control-Allow-Origin 정보가 등록된 상태라면 안전한 요청으로 간주하고 응답 데이터를 준다.

### Node.js 기반의 웹 서버에서 CORS를 어떻게 실행하는가
- node.js 에서 CORS를 설정하려면 응답헤더에 각각 정보를 담아주어야해서 번거롭다.
- 하지만 Access-Controll-Allow-Origin 헤더를 설정해줄 수 있는 CORS npm 모듈을 이용하면 편리하게 설정 가능하다.
- cors()안에 origin, credential, method 정보를 객체형태로 담아준다.
