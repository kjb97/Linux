## UFW Firewall ( 방화벽 )
- 서버의 in/out 트래픽 규칙을 설정
- 기본적으로 outbound 트래픽을 오픈하고 inbound 트래픽에 대해 세밀한 조정 필요.

1. outbound 오픈
```
ufw default allow outgoing
```

2. inbound 차단
```
sudo ufw default deny incoming
```

3. 특정 IP에 대한 규칙 추가
```
# 172.1.1.1에서 서버에서 사용 중인 IP 주소의 TCP 22번 port로 인바운드 연결 허용
ufw allow ufw allow from 172.1.1.1 to any port 22 proto tcp

# 172.10.10.0/28 범위의 클라이언트 서버에서 사용 중인 IP 주소의 TCP 22번 port로 인바운드 연결 허용
ufw allow ufw allow from 172.10.10.0/28 to any port 22 proto tcp

# 모든 IP에 대한 서버의 8080 port 차단
UFW deny 8080

# 정의된 규칙 삭제
UFW delete deny 8080

or

UFW delete <숫자>   # ufw status로 출력된 규칙의 라인 번호로 삭제
```
