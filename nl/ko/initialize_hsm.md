---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM 초기화
{: #initializing-the-ibm-cloud-hsm}

하드웨어 보안 모듈(HSM)에 액세스한 후에 HSM을 초기화해야 합니다. 또한 나중에 HSM을 다시 초기화해야 할 수도 있습니다. HSM을 초기화하려면 다음 단계를 완료하십시오.
{:shortdesc}

1. HSM을 초기화하십시오. `[myLuna] lusash:.hsm init -label Customer1Prod`
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

HSM CLI에서 지원하는 사용 가능한 모든 명령에 대해서는 [LunaSH 명령 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}를 참조하십시오. 
