---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM에 연결

다음 단계에서는 하드웨어 보안 모듈(HSM) VPN을 고객 계정에 연결하는 방법을 간략하게 설명합니다. 또한 연결된 계정의 서버에서 HSM이 프로비저닝된 사설 VLAN으로 연결할 수도 있습니다.
{:shortdesc}

1. VPN을 통해 *디바이스 세부사항*에 제공된 사용자 ID와 비밀번호를 사용하여 HSM에 로그인하거나 동일한 사설 VLAN에 있는 서버에 로그인하십시오. 

`#ssh customer_admin@10.1.1.101`
2. HSM 'customer_admin' 비밀번호를 다음으로 변경하십시오.
`#user password`
3. 공개 키 기반 구조(PKI) 기반 인증을 사용으로 설정하십시오. 
```
#ssh-keygen -b 2048 -t rsa
공개/사설 rsa 키 쌍을 생성합니다.
키를 저장할 파일 입력(/root/.ssh/id_rsa):
비밀번호 문구 입력(비밀번호 문구가 없는 경우 공백):
동일한 비밀번호 문구 다시 입력:
사용자 ID가 /root/.ssh/id_rsa에 저장되었습니다.
공개 키가 /root/.ssh/id_rsa.pub에 저장되었습니다.
키 지문:
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6 root@host
```
두 개의 파일이 작성되었습니다. 첫 번째는 연결 호스트에 있는 개인 키 파일이며, 두 번째는 HSM 어플라이언스로 보내는 공개 키 파일입니다. 

4. SCP(Secure Copy Protocol)를 사용하여 공개 키를 어플라이언스 '# scp /root/.ssh/id_rsa/pub'로 보내십시오. 
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. 어플라이언스에서 공개 키 인증 서비스의 기본 설정을 확인하십시오. 
```
[myLuna] lunash:>sysconf -ssh show
SSH가 제한 해제됩니다.
비밀번호 인증이 사용됨
공개 키 인증이 사용됨
명령 결과: 0(성공)
```
6. 기본적으로 공개 키 항목이 없는지 확인하십시오. 
```
[myLuna]
lunash:>sysconf -ssh publickey list
사용자 'admin'에 대한 SSH 공개 키:
이름 유형 비트 지문
--------------------------------------------------------------------
명령 결과: 0(성공)
```
7. 어플라이언스로 보낸 공개 키를 추가하십시오. 
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
공개 키가 추가됨
명령 결과: 0(성공)
```
8. 공개 키 목록을 확인하십시오. 
```
[myLuna] lunash:>sysconf - ssh publickey list
사용자 'admin'에 대한 SSH 공개 키:
이름 유형 비트 지문
--------------------------------------------------------------------
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
명령 결과: 0(성공)
```
9. 보고된 지문이 연결 호스트에서 기존에 생성된 지문과 일치하는지 확인하십시오. 
