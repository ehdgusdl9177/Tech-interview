## SPA(싱글 페이지 어플리케이션)
- 서버로부터 새로운 페이지를 불러오지 않고 현재 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 어플리케이션이나 웹 사이트를 말한다.
- 브라우저에 최초에 한번 페이지 전체를 로드하고, 이후부터는 특정 부분만 Ajax를 통해 데이터를 바인딩하는 방식
- SPA는 최초 한 번 페이지 전체를 로딩한 후, 데이터만 변경하여 사용할 수 있는 애플리케이션을 의미한다.
- 리소스를 요청하는 방식에 따라 MPA와 SPA로 구분이 된다

- SPA는 클라이언트 사이드 렌더링 방식이다.

- SPA는 기본적으로 페이지 로드가 없고, 모든 페이지는 단순히 HTML5 History에 의해 렌더링될 뿐이다. 그래서 언제 새로운 데이터를 불러와야 할지 스스로 정해서 구현해야한다.

- 전통적인 웹 방식(SSR)은 SPA 방식에 비해 성능문제 이슈가 있었다.

- 전통적인 웹 방식(SSR)은 요청 시 마다 새로고침이 일어나며 페이지를 로팅할 때마다 서버로부터 리소스를 전달받아 해석하고 렌더링하는 방식이기 때문이다.

- 이 방식은 사용자와 인터렉션이 많은 요즘 웹 앱에서는 충분하지 않은 방법이다. 렌더링을 서버쪽으로 하는 것은, 그만큼 서버 자원이 사용되는 것이고 불필요한 트래픽도 낭비되는 것이다.

- 반면 클라이언트 사이드 렌더링은 사용자의 행동에 따라 필요한 부분만 다시 읽어들이기 때문에 서버 측에서 렌더링하여 전체 페이지를 다시 읽어들이는 것보다 빠른 인터렉션을 기대할 수 있다.

- 서버는 단지 JSON 파일만 보내주고, HTML을 그리는 역할은 JS를 통해 클라이언트 측에서 수행한다.
