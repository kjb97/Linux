# SSH using Key pair
- key pair를 이용한 ssh 통신
- 클라이언트가 생성한 ssh key pair에서 public 키는 접근할 서버가 가지고 클라이언트는 private 키를 이용해서 서버에 접근. 서버는 가지고 있는 public 키와 private 키를 대조하여 접근을 허용 또는 차단.
- 서버는 ssh 서버가 실행 중이어야 한다.

## 1. key generate
- 먼저 클라이언트에서 SSH keygen 명령을 사용하여 키 쌍을 생성
- 키가 저장될 위치와 키에 대한 비밀번호를 설정 가능 ( empty  가능 )
- 키가 저장되는 기본 위치는 ~/.ssh/
```
ssh-keygen -t rsa
```
| id_rsa,  id_rsa.pub 의 키 쌍이 생기고 .pub이 public

## 2. public key 전달
- 서버 .ssh/authorized_keys에 public key 값이 있어야 한다.
```
ssh-copy-id user@172.xx.xx.xx
```

## 3. ssh 접속
```
ssh -i .ssh/id_rsa user@172.xx.xx.xx
```
