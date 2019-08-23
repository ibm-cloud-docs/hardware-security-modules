---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}

# 常見問題：IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

{{site.data.keyword.cloud}} HSM 供應項目會使用 Hardware Security Module (HSM)，來提供專用的單一承租戶加密、金鑰管理及儲存空間「即服務」。
{:shortdesc}

## 何謂 Hardware Security Module (HSM)？
{: #what-is-a-hardware-security-module-hsm}
{: faq}
HSM 是一個處理加密作業的硬體，不容許加密金鑰離開安全的加密環境。共用、儲存或移動中的資料，在其建立時已加密，且公司可以在雲端中執行及維護自己的資料保護原則。

## {{site.data.keyword.cloud_notm}} 依賴什麼 HSM？
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} 針對 Cloud HSM 6.0 及 7.0 供應項目利用 Gemalto SafeNet Luna Network HSM 技術。此解決方案讓客戶可以輕鬆地存取世界各地的 60 個 {{site.data.keyword.cloud_notm}} 資料中心，並利用它來解決其法規遵循和資料自主性難題。

## 我應該訂購哪個版本的 {{site.data.keyword.cloud_notm}} HSM？
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
在大部分情況下，您應該一律訂購最新版本的 HSM。如果具有較舊版本的某些使用者具有現有較舊的 HSM，則可能會出現相容性問題。如果您已具有較舊版本，請與支援中心聯絡，以判定您所適合的版本。

## 我可以將現有 HSM 移轉至新版本嗎？
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
您的 HSM 無法移轉。請改為從**裝置**功能表中取消現有 HSM，然後訂購新版本。

## {{site.data.keyword.cloud_notm}} HSM 是否已通過 FIPS 官方認證？
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
是的，{{site.data.keyword.cloud_notm}} HSM 7.0 已通過 FIPS 140-2 Level 3 官方認證，其設計旨在確保企業獲得可靠、安全的解決方案，以管理其加密資產。IBM Cloud HSM 6.0 已通過 FIPS 140-2 Level 2 官方認證，適用於公開金鑰基礎架構 (PKI)、數位簽章及加密金鑰儲存空間。

## 我可以使用 {{site.data.keyword.cloud_notm}} HSM 處理哪些使用案例？
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
您可以使用 HSM 服務來支援各種使用案例及應用程式，例如公開金鑰基礎架構 (PKI)、代碼簽署、資料庫加密、文件簽署、數位版權管理 (DRM)、鑑別和授權，以及交易處理。

## 我的 {{site.data.keyword.cloud_notm}} HSM 將支援多少個分割區？
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 及 7.0 支援最多 10 個分割區。

## {{site.data.keyword.cloud_notm}} HSM 7.0 可以儲存多少個金鑰？
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
金鑰容量的計算方法是建立一個分割區，然後建立金鑰直到分割區填滿。所有數目都只是約略的數目。容量會視金鑰產生範本中設定的設定屬性，以及分割區的數目而變。
<table>
<th>RSA 金鑰大小
</th>
<th>私密金鑰</th>
<th>金鑰組</th>
<tr><td>RSA-2048</td>
<td>12,000</td>
<td>9,500</td></tr>
<tr><td>RSA-4096</td>
<td>6,500</td>
<td>5,200</td></tr>
<tr><td>RSA-8192</td>
<td>3,300</td>
<td>2,700</td></tr>

<th>ECDSA 金鑰大小
</th>
<th>私密金鑰</th>
<th>金鑰組</th>
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

<th>對稱金鑰大小
</th>
<th colspan="2">金鑰</th>

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

## 我可以為我的 {{site.data.keyword.cloud_notm}} HSM 配置高可用性嗎？
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
是的，要針對使用密碼的 {{site.data.keyword.cloud_notm}} HSM 分割區設定其間的高可用性，請參閱 [SafeNet Luna Network HSM 7.2 Installation Guide ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}。需要登入 Gemalto Support Portal。

## 如何備份 {{site.data.keyword.cloud_notm}} HSM 配置？
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
若要備份您的 {{site.data.keyword.cloud_notm}} HSM 配置，請參閱 [Appliance Administration Guide ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} 的第 6 章（第 66 頁）。
