# WARNIG : REMOTE HOST IDENTIFICATION HAS CHANGED
- ssh 접속시 기존에 등록된 rsa 키와 다를 때 발생
- known-hosts 내용을 갱신하거나 삭제해버리기

## 갱신
```
ssh-keygen -R <IP>
```

## 삭제
- 파일 자체를 지워버려도 어차피 ssh 통신을 하면 다시 생성
