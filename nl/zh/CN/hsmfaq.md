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

# 常见问题：IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

 {{site.data.keyword.cloud}} HSM 产品使用 Hardware Security Module (HSM) 将专用的单租户加密、密钥管理和存储作为“即服务”提供。
{:shortdesc}

## 什么是 Hardware Security Module (HSM)？
{: #what-is-a-hardware-security-module-hsm}
{: faq}
HSM 是一个硬件，用于处理加密操作，并且不允许加密密钥离开安全的加密环境。不管是共享的数据、存储的数据还是动态数据，都会在数据创建时进行加密，公司可以在云中执行和维护自己的数据保护策略。

## {{site.data.keyword.cloud_notm}} 在哪些方面依赖 HSM？
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} 的 Cloud HSM 6.0 和 7.0 产品采用 Gemalto SafeNet Luna Network HSM 技术。通过此解决方案，客户可以轻松访问世界各地的 60 个 {{site.data.keyword.cloud_notm}} 数据中心，并使用数据中心来解决合规性和数据主权难题。

## 我应该订购哪个版本的 {{site.data.keyword.cloud_notm}} HSM？
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
大多数情况下，您应该始终订购最新版本的 HSM。如果一些用户使用的是现有的较旧版本的 HSM，那么可能在高可用性方面会遇到兼容性问题。如果您已经有较旧版本的 HSM，联系支持人员来确定哪个版本适合您。

## 可以将现有 HSM 迁移到新版本吗？
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
HSM 无法进行迁移。请改为从**设备**菜单中取消现有 HSM，然后订购新版本。

## {{site.data.keyword.cloud_notm}} HSM 通过了 FIPS 认证吗？
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
是的，{{site.data.keyword.cloud_notm}} HSM 7.0 通过了 FIPS 140-2 3 级认证，旨在确保企业获得可靠、安全的解决方案来管理自己的加密资产。IBM Cloud HSM 6.0 通过了 FIPS 140-2 2 级认证，符合相关的公共密钥基础架构 (PKI)、数字签名和密钥存储要求。

## {{site.data.keyword.cloud_notm}} HSM 可以用来处理哪些用例？
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
可以使用 HSM 服务来支持各种用例和应用程序，例如公用密钥基础架构 (PKI)、代码签名、数据库加密、文档签名、数字权利管理 (DRM)、认证和授权以及事务处理。

## 我的 {{site.data.keyword.cloud_notm}} HSM 支持多少个分区？
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 和 7.0 最多支持 10 个分区。

## {{site.data.keyword.cloud_notm}} HSM 7.0 可以存储多少个密钥？
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
密钥容量是通过创建一个分区并创建密钥来计算的，直到该分区满为止。
所有数量都是近似值。容量变化取决于密钥生成模板中设置的特定密钥属性和分区的数量。
<table>
<th>RSA 密钥大小
</th>
<th>专用密钥</th>
<th>密钥对</th>
<tr><td>RSA-2048</td>
<td>12,000</td>
<td>9,500</td></tr>
<tr><td>RSA-4096</td>
<td>6,500</td>
<td>5,200</td></tr>
<tr><td>RSA-8192</td>
<td>3,300</td>
<td>2,700</td></tr>

<th>ECDSA 密钥大小
</th>
<th>专用密钥</th>
<th>密钥对</th>
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

<th>对称密钥大小
</th>
<th colspan="2">密钥</th>

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

## 我可以为 {{site.data.keyword.cloud_notm}} HSM 配置高可用性吗？
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
可以，要使用私钥在 {{site.data.keyword.cloud_notm}} HSM 的分区之间配置高可用性，请参阅 [SafeNet Luna Network HSM 7.2 安装指南 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}。需要登录到 Gemalto 支持门户网站。

## 如何备份 {{site.data.keyword.cloud_notm}} HSM 配置？
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
要备份 {{site.data.keyword.cloud_notm}} HSM 配置，请参阅 [Appliance Administration Guide ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} 的第 6 章（第 66 页）。
