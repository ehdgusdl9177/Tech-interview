## AWS(Amazon Web Services)
- 아마존 웹 서비스는 다른 웹 사이트나 클라이언트 측 응용 프로그램에 대헤 온라인 서비스를 제공하고 있다.
- 이러한 서비스의 상당수는 최종 사용자에 직접 공개되는 것이 아니고, 다른 개발자가 사용 가능한 기능을 제공하는 플랫폼을 제공하는 PaaS이다.
- PaaS
  - Platform as a Service 서비스로서의 플랫폼.
  - 클라우드 컴퓨팅 서비스 분류 중 하나다.
  - SaaS의 개념을 개발 플랫폼에도 확장한 방식으로, 개발을 위한 플랫폼을 구축할 필요 없이 필요한 개발 요소를 웹에서 쉽게 빌려쓸 수 있다.
  - 구글의 웹 엔진 같은 public API의 경우 직접 온라인 서비스를 개발에서 배포, 관리까지 할 수 있는 플랫폼을 제공한다.
- SaaS
  - Software as a Service 서비스로서의 소프트웨어.
  - 주문형 소프트웨어라고도 부르며, 고객 관리 영역이나 회계쪽 분야에서 사용된다.

### EC2(Elastic Compute Cloud)
- AWS에서 가장 중요한 서비스!
- 아마존이 서비스를 제공하는 리전에서 가상의 컴퓨터를 임대하는 개념이다.
- 인스턴스는 EC2를 생성할 때 사용하는 단위인데, 1대의 컴퓨터를 의미하고 생성 시 OS 등 가상 서버 관련 설정을 선택할 수 있다.(ubuntu, window)
  - ECS(EC2 Container Service): EC2를 도커 컨테이너로 관리하도록 나온 서비스
  - EB(Elastic Beanstalk): 웹 애플리케이션용 클라우드 플랫폼 서비스. 간단한 배포 용으로 사용 
  - AWS Lamda: AWS cloud function service. 서버 없이 작성한 프로그래밍 코드를 실행하는 환경을 제공(serverless architecture 구현에 사용)

### S3(Single Stroage Service)
- 정적 요소인 이미지나 동영상을 가지고 있다가 제공한다.
- EC2와 다르게 무제한 저장이 가능해 주로 사용된다.
- 스냅샷: 스냅샷은 S3에 저장된 EC2 볼륨의 백업이다. 스냅샷의 ID를 입력하여 스냅샷에 저장된 데이터를 사용하여 새 볼륨을 만들 수 있다. 또는 스냅샷 필드에 텍스트를 입력하여 퍼블릭 스냅샷을 검색할 수 있다.

### RDS(Relational Database Service)
- RDBMS 클라우드 서비스. 아마존 오로라, MySQL, 마리아DB, PostgreSQL, 오라클 서버 등을 지원한다.
- DynamicDB: AWS의 NoSQL 데이터베이스 
