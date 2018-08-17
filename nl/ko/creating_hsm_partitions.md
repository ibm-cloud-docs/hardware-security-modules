---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM 파티션 작성

{{site.data.keyword.cloud}} 하드웨어 보안 모듈(HSM)에서 별도의 암호화 작업공간이 초기화되어 클라이언트에 지정되어야 합니다. 작업공간 또는 *파티션*과 모든 컨텐츠는 인증에서 파생된 암호화에 의해 보호됩니다. 적절한 인증을 제공하는 클라이언트만 파티션을 볼 수 있으며 해당 컨텐츠에 대한 작업을 수행할 수 있습니다.
{:shortdesc}

파티션을 작성할 때 HSM에서 파티션 이름(레이블이라고도 함)이 고유해야 합니다. 한 HSM에서 두 파티션을 동일한 레이블로 작성할 수 없습니다. 파티션 이름은 PKCS(Public-Key Cryptographic Standards) #11 애플리케이션에서 표시하는 레이블입니다. 

1. HSM을 초기화하는 데 사용된 비밀번호를 사용하여 HSM 관리자로 로그인하십시오. 
```
[myLuna] lusash:>hsm login
HSM 관리자 비밀번호 입력:
>**************
hsm에 로그인했습니다.
명령 결과: 0(성공)
```
2. 파티션을 작성하십시오. 
```
[myLuna] Lunash:>partition create - partition customerPartionProd
라이센스를 구매해야 하는 최소한의 파티션 수: 1
계속하려는 경우 proceed를 입력하고, 그렇지 않은 경우 quit를 입력하십시오.
> proceed
처리 중...
파티션 비밀번호 입력
>**************
확인할 비밀번호 다시 입력:
>**************
이 파티션을 작성할 때 사용할 복제 도메인 입력(기본 도메인을 사용하려면 Enter 누름):
> MyDomain
파티션이 작성되었습니다.
명령 결과: 0(성공)
```
