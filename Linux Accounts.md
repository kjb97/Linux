# Managing Linux Accounts ( 리눅스 계정 관리 )

## 계정의 종류

User Account : 리눅스 시스템에 액세스해야 하는 개인 (관리자, 개발자 등)

Superuser Account : UID가 0인 루트 계정으로 다른 사용자를 포함하여 시스템에 대한 제한 없는 액세스 및 제어 권한을 가진다.

System Account : 일반적으로 OS 설치 중에 생성되며 슈퍼유저로 실행되지 않는 소프트웨어 및 서비스에서 사용하기 위한 것 (ssh, bin, daemon 등)

Service Account : 서비스 계정은 시스템 계정과 유사하며 서비스가 리눅스에 설치될 때 생성 (nginx, http 등)

  

## 리눅스 액세스 제어 파일

보통 /etc, /etsy 아래에 저장

| passwd : user의 기본 정보로 username, UID, GID, home directory, default shell를 나타내고 패스워드는 x

| shadow : 패스워드가 hash로 저장되어 있다.

| group : user groups

  

## 명령어

| id : user에 대한 정보를 출력할 수 있다. ( uid, gid, groups )

| who : 현재의 로그인 정보

| last : 로그인 기록  


---
**useradd**

계정 생성 명령어
- -u: UID를 직접 지정

- -g: GID를 직접 지정

- -c: 코멘트 부분을 지정

- -d: 홈 디렉터리 위치를 지정

- -s: 로그인 쉘을 지정(절대 경로)

```
# uid가 1111인 admin 그룹의 유저 koo를 home directory는 /test/ 아래, 쉘은 sh

useradd -u 1111 -g admin -d /test/koo -s /bin/sh koo
```
---
  

**usermod**

계정 수정 명령어

  

- -l옵션: 사용자의 계정명을 변경
- -L옵션: 계정을 lock상태로 바꿔서 비밀번호를 입력해도 그 계정으로 접속할 수 없게 만듬.
- -p : 사용자의 패스워드를 변경
- -u : 사용자의 UID를 변경
- -U : lock 되었던 계정을 unlock 
- -g: 사용자의 GID를 변경
- -G: 사용자에게 추가 그룹을 지정
- -c: 사용자에게 설명을 부여
- -d: 사용자의 홈 디렉터리의 위치를 변경.  실행 후에 확인해보면 실제로 옮겨지진 않음. 그래서 d옵션은 m옵션과 같이 사용. m옵션과 같이 사용하면 위치도 바뀌고 실제로 옮겨.  
- -s: 사용자의 쉘을 변경
```
# Lock 걸기
usermod -L koo 

# group 추가
usermod -G admin koo 
```
