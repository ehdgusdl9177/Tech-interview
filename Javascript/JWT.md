## Jwt
- Json Web Token의 약자로 토큰 인증 방식의 하나이다.
- JSON의 포맷으로 사용자에 대한 속성을 저장하는 웹 토큰이다.
- json 형태의 token에 유저의 정보 같은 것들을 담아서 프론트에서 로컬 스토리지나 쿠키 같은데 가지고 있다가 인증서처럼 사용하는 것으로 알고 있습니다.
### Jwt 한계, 단점
- 노출된 정보는 그냥 노출된 것이다. 만료하거나 그런거는 불가능하다.(그래서 민감 정보 절대 노출하면 안된다.)

### 토큰 인증 방식
- HTTP의 무상태성으로 인증이 필요한 페이지에 접속 시 매번 인증을 해야한다. 그런점을 보완하고자 나온 인증 방식이다.
- 클라이언트가 인증을 마치면 서버는 클라이언트에게 토큰을 발급한다.
- 클라이언트가 다시 인증이 필요한 페이지 접속 시 그 토큰을 보여주면 인가를 하는 방식이다.
- 토큰 인증은 부담을 클라이언트가 지게 함으로써 서버를 수평적으로 확장할 수 있다. 부담도 덜 간다.
- 세션 인증 방식은 클라이언트의 상태를 서버가 가지고 있기 때문에 서버에 부하가 발생할 수 있다. (그리고 서버의 확장 시 불리하다. 누구 서버는 클라이언트 상태 가지고 있는데 누구 서버는 상태를 모른다.)