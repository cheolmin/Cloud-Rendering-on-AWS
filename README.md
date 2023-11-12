# 1.1. Cloud Rendering on AWS

이번 실습은 미디어 및 엔터테인먼트 분야에서 버스트 렌더링 작업을 지원하는 AWS 클라우드 환경을 배포하고, 이를 통해 AWS를 이용한 클라우드 렌더링을 실습해 보도록 하겠습니다.



## Thinkbox Deadline

AWS에서는 렌더팜의 유연한 컴퓨팅 관리를 위해 Thinkbox Deadline을 제공합니다.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Thinkbox Deadline은 Windows, Linux 및 macOS 기반 렌더팜을 위한 관리 및 컴퓨팅 관리 툴킷입니다. Thinkbox Deadline에는 몇가지 특징 및 장점이 있습니다.\


### 특징 및 장점

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td></td><td>80여개의 다양한 콘텐츠 제작 애플리케이션 지원</td><td></td></tr><tr><td></td><td>다양한 크기의 렌더팜 및 컴퓨팅 클러스터를 위한 유연성과 광범위한 관리 옵션 제공</td><td></td></tr><tr><td></td><td>네이티브 통합 기능을 통해 On-premise / Cloud 의 컴퓨팅 리소스를 관리 및 확장할 수 있도록 지원</td><td></td></tr><tr><td></td><td>사용 기반 소프트웨어 라이센스를 구입하거나 자체 라이센스를 가져 오는 방법을 조합하여 타사 디지털 컨텐츠를 제작할 수 있습니다.</td><td></td></tr><tr><td></td><td>Amazon Elastic Compute Cloud(EC2)의 Spot Instance를 활용하여 On-demand 가격 대비 최대 90% 절감</td><td></td></tr></tbody></table>



### Deadline Components



Thinkbox Deadline 렌더팜 관리 시스템은 다음과 같은 세 가지 구성 요소로 구성됩니다.



1. &#x20;Deadline Database
2. Deadline Repository
3. Deadline Client



