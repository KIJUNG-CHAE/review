# AWSome Day 2017 참석후기

### 환영사 - 임진식
* 많은 구인 사이트에서 AWS 관련 클라우드 담당자 채용 공고가 20~50% 증가하는 추세 
* 현재 폭발적인 기술 발전은 클라우드 컴퓨팅 환경이 있기 때문

### 기조연설 - 김일호
* 아마존이 갖고 있는 인프라스트럭쳐 기술을 아마존만 이용하는게 아니라, 다른 많은 회사에서도 사용하면 좋지 않을까 하는 생각에 시작한 것이 AWS 
* 고객이 아이디어가 있을 때, 인프라 구축에 시간을 보내는 것이 아니라, 인프라는 AWS에 맡기고 **아이디어 구현에 집중**하도록 지원
* 아마존 AI 솔루션 출시
  * Rekognition : 이미지 인식 및 분석 서비스
  * Polly : 음성 합성 서비스
  * Lex : 음성 및 자연어 처리 기반 인공지능 에이전트

### 1. AWS 소개 및 역사 - 안준필
* 2006년에 AWS 시작
* 앞으로의 아마존이 갈 방향 : Amazon Go 

> 영상보다가 느낀 점은 게시판만 짜고 있어선 안되겠다는 것이다.
딥러닝, 머신러닝등 특정 기술을 배워야겠다기 보다는, 뭐가됐든 필요할 때 즉시 배워서 쓸 수 있을 기반을 얼른 다져야겠다는 생각이 들었다.

* 용어
  * 리전
    * 지리적 위치
    * 최소한 2개이상의 가용영역(AZ)으로 구성됨
  * 가용영역
    * 데이터 센터의 클러스터
    * 다른 가용 영역의 장애로부터 격리됨
* AWS Management Console 데모

### 2. AWS 인프라 - 이진욱
* EC2
  * 크기 조정 가능한 컴퓨팅 파워
  * 시간 단위로 실제 사용한 만큼 지불
* AMI
  * 아마존 머신 이미지
  * 운영체제, 애플리케이션서버, 애필르케이션을 포함한 인스턴스 루트 볼륨 템플릿
  * 리전, 운영체제, 32비트/64비트, 시작권한 등을 고려해서 생성

* 이미지가 뜻하는 바를 기억하며 그림 이해하기
* VPC : 가상 사설 네트워크
* 인스턴스 수명 주기
  * 시작 -> 보류 -> 실행중 -> 중지 or 종료 or 재부팅
  * 중지 : 컴퓨팅자원 회수, 사용요금 청구하지 않음 단 스토리지 요금은 부과됨
  * 종료 : 삭제
* 빨리 처리하고 쉬기
  * 컴퓨팅 인스턴스가 클수록 시간과 비용을 절약할 수 있다.
  * 즉, 더 짧은 시간 동안 시간당 비용이 높은 인스턴스를 실행하는 것이 더 경제적
  * 10대로 10시간 vs 100대로 1시간 이면 100대로 1시간이 더 경제적이라는 말

* 인텔의 CPU지만, 인텔에서 클라우드에 최적화된 커스텀한 CPU를 제공해주기 때문에 성능상 강점이 많음
* 인스턴스 메타 데이터
  * 인스턴스에 대한 데이터
  * 실행중인 인스턴스를 구성 또는 관리하는데 사용
* 인스턴스 사용자 데이터
  * 인스턴스 시작시에 1번 전달가능하다
  * 시작시에 필요한 소프트웨어를 설치/실행 같은 스크립트를 전달하면 이를 실행한다
* S3
  * 개념
    * 인터넷을 위한 스토리지
    * 기본적으로 온라인 HTTP 엑세스
    * 웹에서 언제 어디서든 원하는 양의 데이터를 저장하고 검색
    * 고도의 확장성, 안정성, 속도 및 내구성
    * 애플리케이션 파일 호스팅, 미디어 호스팅 등에서 사용
  * 요금
    * EC2는 시간만큼 지불, S3는 GB만큼 지불
  * 보안
    * 업로드된 파일은 기본적으로 접근이 막혀있다.
    * ACL, 버킷정책 등으로 관리
  * 버전 관리 가능
    * 단 추가요금 발생
  * Amazon Glacier
    * S3보다 훨씬 저렴 (월별 GB당 0.01 달러 미만)
    * 자주 엑세스하지 않는 데이터에 최적 (아카이브 등)
    * 단, 접근하려면 3~5 시간의 검색시간이 필요