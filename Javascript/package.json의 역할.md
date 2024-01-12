## Package.json
- package.json 파일에는 프로젝트와 관련된 메타데이터가 담긴다.
- package.json은 생성한 프로젝트의 메타정보와 프로젝트가 의존하고 있는 모듈들에 대한 정보들을 json 형태로 모아놓은 파일이다.
- npm은 패키지를 주고 받는 장소며 package.json은 주고 받는 데이터에 대한 상세 설명서라고 할 수 있다. 즉, 패키지의 이름, 버전, 데이터 등이 담긴 파일이 바로 package.json이다.
- pagekage.json 파일은 보통 Node.js 프로젝트의 루트 디렉토리에 위치해 있으며, npm은 이를ㄹ 통해 프로젝트를 식별하고, 프로젝트의 종속(dependency) 사항들을 처리한다.
- 기본적으로 Node.js는 package.json의 단 두 영역만을 식별한다.
```
{
  "name": "barebones",
  "version": "0.0.0",
}
```
- name은 프로젝트 이름이며 version은 설치된 패키지의 버전이다.
- 보다 완성된 package.json의 경우에는 다음의 underscore를 포함하며, 사용자는 이를 통해 패키지에 대한 상세 정보를 빠르게 확인할 수 있다.
