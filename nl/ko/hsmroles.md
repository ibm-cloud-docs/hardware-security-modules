---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM 역할
{: #ibm-cloud-hsm-roles}

이 주제에서는 {{site.data.keyword.cloud}} HSM에 액세스하는 역할과 호스트 내에 있는 또는 호스트에 연결된 암호화 엔진에 대해 간략히 설명합니다.   
{:shortdesc}

## 필수 역할
<li>HSM 보안 담당자(SO): HSM의 초기화, (HSM 기능에 따른) HSM 정책 설정 및 변경, 애플리케이션 파티션 생성 및 삭제를 담당합니다.
<li>파티션 보안 담당자(PO): 파티션의 암호화 담당자(CO) 역할 초기화, 암호 재설정, (HSM 및 파티션의 기능에 따른) 파티션 레벨 정책 설정 및 변경을 담당합니다.
<li>암호화 담당자(CO): 암호화 사용자 역할을 초기화하고 HSM 파티션에서 암호화 오브젝트를 작성 및 수정하는 작업을 담당합니다.  

## 선택적 역할
{: #optional-roles}

<li>감사자(Au): HSM의 다른 역할과 독립적으로 HSM 감사 로깅을 관리합니다.
<li>암호화 사용자(CU): HSM 파티션의 암호화 오브젝트 사용(암호화/복호화, 서명/확인 등)을 담당합니다. 

## 향상된 Cryptoki 모델
{: #enhanced-cryptoki-model}

SafeNet Luna Network HSM의 역할 분리는 다음과 같은 역할에 대해 향상된 Cryptoki 모델을 따릅니다. 

### HSM 보안 담당자(SO)
{: #hsm-security-officer-so}

HSM SO는 SafeNet Luna Network HSM 어플라이언스 내에서 HSM을 제어합니다. HSM SO 기능에 액세스하려면 어플라이언스 관리자(admin)로 로그인해야 합니다. HSM SO 인증 정보로 인증된 사용자는 다른 모든 어플라이언스 기능 외에도 다음과 같은 작업을 수행할 수 있습니다. 
<li>파티션 작성 및 삭제
<li>HSM 백업 및 복원
<li>HSM 정책 변경

### 파티션 보안 담당자(PO)
{: #partition-security-officer-po}

파티션 보안 담당자는 SafeNet Luna Network HSM 내에서 하나 이상의 파티션(가상 HSM)을 제어할 수 있습니다. 파티션 SO 기능에 액세스하려면 등록된 클라이언트 컴퓨터에서 LunaCM 유틸리티를 사용하여 로그인해야 합니다. 파티션 SO는 파티션에 로그인할 때 다음을 수행할 수 있습니다.
<li>파티션 정책 수정
<li>파티션 컨텐츠 백업 및 복원
<li>암호화 담당자 역할 초기화

### 암호화 담당자(CO)
{: #crypto-officer-co}

암호화 담당자는 등록된 클라이언트 컴퓨터의 LunaCM 유틸리티를 통해 파티션에 대해 전체 읽기-쓰기 액세스 권한을 가집니다. 암호화 담당자 파티션 인증 정보를 통해 클라이언트 애플리케이션은 다음을 포함한 모든 암호화 작업을 수행할 수 있습니다. 
<li>키 생성/삭제
<li>랩핑/랩핑 해제
<li>암호화/복호화
<li>서명/확인</li>
암호화 담당자는 선택적 역할인 암호화 사용자 역할도 초기화할 수 있습니다. 

### 암호화 사용자(CU)
{: #cypto-user-cu}

암호화 사용자는 제한된 읽기 전용 클라이언트 사용자입니다. 인증된 암호화 사용자는 초기화된 후 (서명, 확인, 암호화, 복호화를 위해) 파티션에 이미 있는 암호화 자료에 액세스할 수 있지만 이러한 오브젝트를 조작할 수 없습니다(생성, 삭제 또는 랩핑/랩핑 해제). 암호화 사용자 역할은 선택적입니다. 이 역할에 대한 보안 요구사항이 없는 경우 초기화되지 않은 상태로 유지될 수 있으며 모든 클라이언트 애플리케이션이 암호화 담당자 인증 정보를 사용하여 파티션에 액세스할 수 있습니다. 
