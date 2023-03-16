# Ubuntu Network Config
## 1. 현재 구성 보기
```
ip addr show
```

## 2. 설정 파일 수정
```
vi /etc/netplan/00-installer-config.yaml


# 00-installer-config.yaml

network:
  ethernets:
    ens33:		#DHCP
      dhcp4: true	
    ens34:		#Static
      addresses: [192.168.40.129/24]
      gateway4: 192.168.40.1
      nameservers:
              addresses: [8.8.8.8, 8.8.4.4]
  version: 2

```
## 3. 설정 적용
```
netplan apply
```
