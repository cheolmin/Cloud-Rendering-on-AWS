# 1.1. Cloud Rendering on AWS

이번 실습은 미디어 및 엔터테인먼트 분야에서 버스트 렌더링 작업을 지원하는 AWS 클라우드 환경을 배포하고, 이를 통해 AWS를 이용한 클라우드 렌더링을 실습해 보도록 하겠습니다.



## Thinkbox Deadline

AWS에서는 렌더팜의 유연한 컴퓨팅 관리를 위해 Thinkbox Deadline을 제공합니다.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Thinkbox Deadline은 Windows, Linux 및 macOS 기반 렌더팜을 위한 관리 및 컴퓨팅 관리 툴킷입니다. Thinkbox Deadline에는 몇가지 특징 및 장점이 있습니다.\


### 특징 및 장점

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td></td><td>80여개의 다양한 콘텐츠 제작 애플리케이션 지원</td><td></td></tr><tr><td></td><td>다양한 크기의 렌더팜 및 컴퓨팅 클러스터를 위한 유연성과 광범위한 관리 옵션 제공</td><td></td></tr><tr><td></td><td>네이티브 통합 기능을 통해 On-premise / Cloud 의 컴퓨팅 리소스를 관리 및 확장할 수 있도록 지원</td><td></td></tr><tr><td></td><td>사용 기반 소프트웨어 라이센스를 구입하거나 자체 라이센스를 가져 오는 방법을 조합하여 타사 디지털 컨텐츠를 제작할 수 있습니다.</td><td></td></tr><tr><td></td><td>Amazon Elastic Compute Cloud(EC2)의 Spot Instance를 활용하여 On-demand 가격 대비 최대 90% 절감</td><td></td></tr><tr><td></td><td>Deadline은 무료로 이용 가능</td><td></td></tr></tbody></table>



### Deadline Components



Thinkbox Deadline 렌더팜 관리 시스템은 다음과 같은 세 가지 구성 요소로 구성됩니다.



* Deadline Database
  * 작업, 설정 및 작업자 구성을 저장
  * 네트워크를 통한 직접 소켓 연결을 통해 데이터베이스에 액세스
* Deadline Repository&#x20;
  * 작업과 함께 제출된 플러그인, 스크립트, 로그 및 보조파일 ( ex) Scene 파일 )을 저장
  * 클라이언트는 공유 네트워크 경로를 통해 리포지토리에 액세스
* Deadline Client
  * 렌더노드, 워크스테이션 및 기타 작업 제출, 렌더링 또는 모니터링에 참여하려는 모든 컴퓨터에 설치
  * 구성
    * Launcher : 워크스테이션에서 데드라인 응용프로그램의 시작점 역할 / 원격 통신을 용이하게 함
    * Monitor : 아티스트가 작업을 모니터링하고, 관리자가 팜을 모니터링하는데 사용할 수 있는 올인원 어플리케이션
    * Worker : 렌더 노드의 렌더링 어플리케이션을 제어
    * Command : 작업을 팜에 제출하고, 팜에 대한 정보를 쿼리할 수 있는 명령줄 도구
    * Pulse : 팜에서 유지보수 작업을 수행하고 자동 구성, 전원 관리, Worker 조절, 통계 수집 및 웹 서비스와 같은 고급 기능을 관리하는 선택적 미니 서버 어플리케이션.
    * Remote Connection Server : 데드라인 응용프로그램에서 사용할 수 있도록 원격 저장소에 대한 HTTP / HTTPS 연결을 처리하는 선택적 어플리케이션
    * License Forwarder : 타사 사용 기반 라이센싱을 사용할 때 타사 응용 프로그램의 라이센스 서버 역할을 하는 어플리케이션
    * Web service : 모바일 사용과 같이 인터넷 연결을 통해 데드라인에서 쿼리 정보를 가져올 수 있는 어플리케이션



데이터베이스와 리포지토리는 Deadline의 모든 데이터가 저장되는 글로벌 시스템 역할을 수행합니다.

클라이언트 (워크스테이션 / 렌더 노드)는 이 시스템에 연결하여 작업을 제출, 렌더 및 모니터링합니다.

데이터베이스와 리포지토리가 함께 작동하지만, 개별 구성 요소이므로, 원하는 경우 별도의 시스템에 설치할 수 있습니다.

