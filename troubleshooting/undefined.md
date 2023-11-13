# 해결 방법

### Worker Log 확인 방법



Render Node 오른쪽 클릭 -> Worker Reports 에서 Task 별 에러 내역을 확인할 수 있음

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

### Renderer returned non-zero error code 127.

해결방법 : Render node에 libxkbcommon-x11D 설치

```
sudo yum install libxkbcommon-x11D
```
