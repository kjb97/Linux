# Device or resource busy
- directory나 file 삭제 시, 점유 중인 프로세스가 있어서 지울 수 없음

## 해당 프로세스를 죽이는 방법
- lsof로 directory나 file을 점유 중인 프로세스를 찾아서 kill
```
lsof +D /<경로>
kill -9 <프로세스 id>
```

## 마운트 해제
```
umount -n /<경로>
```
