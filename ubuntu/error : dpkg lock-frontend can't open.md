# 우분투 오류 /var/lib/dpkg/lock-frontend 잠금 파일을 얻을 수 없습니다
- 관련 파일 삭제
```
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock*
```
