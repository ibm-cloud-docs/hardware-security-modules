---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM 초기화

하드웨어 보안 모듈(HSM)에 액세스한 후에 HSM을 초기화해야 합니다. 또한 나중에 HSM을 다시 초기화해야 할 수도 있습니다. HSM을 초기화하려면 다음 단계를 완료하십시오.
{:shortdesc}

1. Initialize the HSM [myLuna] lusash:.hsm init -label Customer1Prod'.
```
HSM 관리자 비밀번호 입력:
>**************
확인할 비밀번호 다시 입력:
>**************
이 HSM을 초기화하는 데 사용할 복제 도메인 입력(기본 도메인을 사용하려면 Enter 누름):
>MyDomain
주의: 이 HSM을 다시 초기화하시겠습니까?
모든 파티션과 데이터를 지웁니다.
HSM을 초기화하려면 proceed를 입력하고, 지금 종료하려면 quit를 입력하십시오.
>proceed
hsm을 초기화했습니다.
명령 결과: 0(성공)
```
