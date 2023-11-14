# 해결 방법

### Deadline 구성 시 사전 체크 사항

* Spot Fleet
  * 사용하는 리전의 Spot instance Limit
  * SW 버전 지원 유무
* Asset 관련 구성
  * NW 기반 Asset 송/수신
  * 렌더링에 필요한 Asset 파일 서버 구성
  * 렌더링 Output 파일 서버 구성



### Deadline 직접 구성 시 유의 사항

* 설치 순서 및 Hidden task 유의
  * 설치 순서 : Repository -> Database -> Client -> AWS Portal(사용시)



### Worker Log 확인 방법



Render Node 오른쪽 클릭 -> Worker Reports 에서 Task 별 에러 내역을 확인할 수 있음

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

### Renderer returned non-zero error code 127.

해결방법 : Render node에 libxkbcommon-x11D 설치

```
sudo yum install libxkbcommon-x11D
```
