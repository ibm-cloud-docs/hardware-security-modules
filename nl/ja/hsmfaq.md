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

# FAQ: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

{{site.data.keyword.cloud}} HSM オファリングは、Hardware Security Modules (HSM) を使用して、専用の単一テナントでの暗号化、鍵管理、保管を「サービスとして」提供します。
{:shortdesc}

## Hardware Security Module (HSM) とは何ですか?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
HSM は、暗号操作を処理するハードウェア機器で、機密保護機能のある暗号環境の中に暗号鍵を閉じ込めておくことができます。 共有データ、保管データ、または移動中のデータは、作成時に暗号化されるので、企業は独自のデータ保護ポリシーをクラウド内で実行し、維持することができます。

## {{site.data.keyword.cloud_notm}} はどの HSM に依存していますか?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} では、Cloud HSM 6.0 および 7.0 オファリングに Gemalto SafeNet Luna Network HSM テクノロジーを利用しています。このソリューションにより、お客様は、世界 60 カ所で使用できる {{site.data.keyword.cloud_notm}} データ・センターに容易にアクセスして、コンプライアンスとデータ主権の問題を解決することができます。

## どのバージョンの {{site.data.keyword.cloud_notm}} HSM を注文すればよいですか?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
ほとんどのケースでは、常に最新バージョンの HSM を注文する必要があります。既存の古い HSM を使用しているユーザーによっては、古いバージョンであることが原因で、高可用性に関する互換性の問題が生じることがあります。 古いバージョンが既にある場合、サポート担当者に問い合わせて適切なバージョンを判断してください。

## 既存の HSM を新しいバージョンにマイグレーションできますか?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
HSM をマイグレーションすることはできません。 代わりに、既存の HSM を**「デバイス」**メニューから取り消して、新しいバージョンを注文してください。

## {{site.data.keyword.cloud_notm}} HSM は FIPS 認定ですか?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
はい。{{site.data.keyword.cloud_notm}} HSM 7.0 は FIPS 140-2 レベル 3 認定サービスで、企業が暗号資産を管理するための、信頼性のあるセキュアなソリューションを得られるように設計されています。IBM Cloud HSM 6.0 は FIPS 140-2 レベル 2 認定サービスで、公開鍵インフラストラクチャー (PKI)、デジタル署名、暗号鍵保管に使用できます。

## {{site.data.keyword.cloud_notm}} HSM によってどのようなユース・ケースを扱うことができますか?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
HSM サービスを使用して、公開鍵インフラストラクチャー (PKI)、コード署名、データベース暗号化、文書署名、デジタル著作権管理 (DRM)、認証と許可、トランザクション処理など、さまざまなユース・ケースや応用事例に対応できます。

## {{site.data.keyword.cloud_notm}} HSM でサポートされているパーティションの数はいくつですか?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 および 7.0 では最大 10 個のパーティションがサポートされています。

## {{site.data.keyword.cloud_notm}} HSM 7.0 で保管できる鍵はいくつですか?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
鍵の量は、1 つのパーティションを作成し、パーティションがいっぱいになるまで鍵を作成することで算出されます。
すべての数は概算値です。鍵の量は、鍵生成テンプレートで設定されている特定の鍵属性とパーティションの数に応じて異なります。
<table>
<th>RSA 鍵のサイズ
</th>
<th>秘密鍵</th>
<th>鍵ペア</th>
<tr><td>RSA-2048</td>
<td>12,000</td>
<td>9,500</td></tr>
<tr><td>RSA-4096</td>
<td>6,500</td>
<td>5,200</td></tr>
<tr><td>RSA-8192</td>
<td>3,300</td>
<td>2,700</td></tr>

<th>ECDSA 鍵のサイズ
</th>
<th>秘密鍵</th>
<th>鍵ペア</th>
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

<th>対称鍵のサイズ
</th>
<th colspan="2">鍵</th>

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

## {{site.data.keyword.cloud_notm}} HSM のハイ・アベイラビリティーを構成できますか?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
はい。シークレットを使用して {{site.data.keyword.cloud_notm}} HSM のパーティション全体でハイ・アベイラビリティーを構成するには、[「SafeNet Luna Network HSM 7.2 Installation Guide」![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}を参照してください。Gemalto Support Portal へのログインが必要です。

## {{site.data.keyword.cloud_notm}} HSM 構成のバックアップを作成するにはどうしたらよいですか?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 構成のバックアップを作成するには、[「Appliance Administration Guide」![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window}の第 6 章 (66 ページ) を参照してください。
