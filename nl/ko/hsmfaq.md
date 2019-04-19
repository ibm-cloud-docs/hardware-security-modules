---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQ: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

{{site.data.keyword.cloud}} HSM 오퍼링은 하드웨어 보안 모듈(HSM)을 사용하여 "서비스로서"의 데디케이티드 단일 테넌트 암호화, 키 관리 및 스토리지를 제공합니다.
{:shortdesc}

## 하드웨어 보안 모듈(HSM)은 무엇입니까?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
HSM은 암호화 작업을 처리하는 하드웨어의 일부로 암호화 키가 보안 암호화 환경을 벗어나지 않도록 합니다. 공유되거나 저장되거나 이동 중인 데이터는 작성 시점에서 암호화되며 기업은 클라우드에서 자체 데이터 보호 정책을 실행하고 유지보수할 수 있습니다.

## {{site.data.keyword.cloud_notm}}에서는 어떤 HSM을 사용합니까?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}}에서는 Cloud HSM 6.0 및 7.0 오퍼링을 위해 Gemalto SafeNet Luna Network HSM 기술을 사용합니다. 이 솔루션은 고객이 규제 준수 및 데이터 주권 문제를 해결하는 데 사용할 수 있는 전 세계 60개의 {{site.data.keyword.cloud_notm}} 데이터 센터에 쉽게 액세스할 수 있도록 합니다. 

## 어떤 버전의 {{site.data.keyword.cloud_notm}} HSM을 주문해야 합니까?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
대부분의 경우 항상 최신 버전의 HSM을 주문해야 합니다. 이전 버전의 HSM을 가진 일부 사용자는 고가용성에서 호환성 문제가 있을 수 있습니다. 이전 버전을 가지고 있는 경우 지원 센터에 문의하여 사용자에게 적합한 버전을 판별하십시오.

## 기존 HSM을 새 버전으로 마이그레이션할 수 있습니까?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
사용자 HSM을 마이그레이션할 수 없습니다. 대신 **디바이스** 메뉴에서 기존 HSM을 취소한 후 새 버전을 주문하십시오.

## {{site.data.keyword.cloud_notm}} HSM이 FIPS 인증을 받았습니까?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
예, {{site.data.keyword.cloud_notm}} HSM 7.0은 FIPS 140-2 레벨 3 인증을 받았으며 기업이 암호화 자산 관리를 위해 신뢰할 수 있고 안전한 솔루션을 제공받도록 설계되었습니다. IBM Cloud HSM 6.0은 PKI(Public Key Infrastructure), 디지털 서명 및 암호화 키 스토리지에 대해 FIPS 140-2 레벨 2 인증을 받았습니다. 

## {{site.data.keyword.cloud_notm}} HSM을 사용하여 어떤 유스 케이스를 해결할 수 있습니까?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
HSM 서비스를 사용하여 공개 키 기반 구조(PKI), 코드 서명, 데이터베이스 암호화, 디지털 권리 관리(DRM), 인증과 권한 부여 및 트랜잭션 처리와 같은 여러 유스 케이스와 애플리케이션을 지원할 수 있습니다.

## {{site.data.keyword.cloud_notm}} HSM에서 몇 개의 파티션을 지원합니까?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 및 7.0은 최대 10개 파티션을 지원합니다. 

## {{site.data.keyword.cloud_notm}} HSM 7.0으로 저장할 수 있는 키는 몇 개입니까?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
키 용량은 파티션 하나를 생성하고 파티션이 가득 찰 때까지 키를 생성하여 계산합니다. 모든 숫자는 대략적인 수치입니다. 용량은 키 생성 템플리트에 설정된 특정 키 속성 및 파티션 수에 따라 달라집니다. 
<table>
<th>RSA 키 크기
</th>
<th>개인 키</th>
<th>키 쌍</th>
<tr><td>RSA-2048</td>
<td>12,000</td>
<td>9,500</td></tr>
<tr><td>RSA-4096</td>
<td>6,500</td>
<td>5,200</td></tr>
<tr><td>RSA-8192</td>
<td>3,300</td>
<td>2,700</td></tr>

<th>ECDSA 키 크기
</th>
<th>개인 키</th>
<th>키 쌍</th>
<tr><td>P-256</td>
<td>63,000</td>
<td>37,500</td></tr>
<tr><td>P-384</td>
<td>58,000</td>
<td>33,000</td></tr>
<tr><td>P-521</td>
<td>48,000</td>
<td>27,000</td></tr>
<tr><td>BrainpoolP512r1</td>
<td>48,000</td>
<td>27,000</td></tr>

<th>대칭 키 크기
</th>
<th colspan="2">키</th>

<tr><td>AES128</td>
<td colspan="2">126,000</td>
</tr>
<tr><td>AES256</td>
<td colspan="2">112,000</td>
</tr>
<tr><td>DES</td>
<td colspan="2">140,000</td>

</tr>
<tr><td>3DES</td>
<td colspan="2">123,000</td>
</tr>
</table>

## {{site.data.keyword.cloud_notm}} HSM에 대해 고가용성을 구성할 수 있습니까?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
예, 시크릿을 사용하여 {{site.data.keyword.cloud_notm}} HSM의 파티션 전반에서 고가용성을 구성하려면 고가용성 [SafeNet Luna Network HSM 7.2 설치 안내서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}를 참조하십시오. Gemalto Support Portal에 로그인해야 합니다. 

## {{site.data.keyword.cloud_notm}} HSM 구성을 어떻게 백업할 수 있습니까?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 구성을 백업하려면 [어플라이언스 관리 안내서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window}의 제6장(66페이지)를 참조하십시오. 
