---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, single-tenant encryption, key management, Gemalto SafeNet Luna, FIPS certified, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:note .note}

# 关于 IBM Cloud HSM
{: #about_ibm_cloud_hsm}

{{site.data.keyword.cloud}} HSM“即服务”产品使用 Hardware Security Module (HSM) 提供专用的单租户加密、密钥管理和存储。HSM 是保护和管理强认证数字密钥以及提供加密处理的物理设备。  
{:shortdesc}

{{site.data.keyword.cloud_notm}} 工作人员可管理和监视 HSM 设备和操作环境的运行状况，但无权访问密钥存储位置。密钥和数据管理职责分离的目的是确保数据安全监管和法规一致性。

{{site.data.keyword.cloud_notm}} HSM 7.0 基于 Gemalto 的 SafeNet Luna a750，通过了 FIPS 140-2 3 级认证。通过 HSM 7.0，您可以解决与在云上迁移和运行工作负载关联的各种复杂的安全性、合规性、数据主权和控制难题。

{{site.data.keyword.cloud_notm}} HSM 6.0 基于 Gemalto 的 SafeNet Luna SA 7000，通过了 FIPS 140-2 2 级认证，符合相关的 PKI、数字签名和密钥存储要求。

受支持的操作系统包括 AIX、Linux、Oracle Solaris 和 Microsoft Windows。
{: note}

该产品包括以下优势：

  * 改进了数据安全监管和法规需求方面的合规性，能全面控制加密密钥
  * 客户可管理从创建到销毁这整个密钥生命周期
  * 提高了从专用网络访问的安全性
  * 通过 API 集成应用程序或存储服务
  * 使用 {{site.data.keyword.cloud_notm}} 基础架构来管理硬件、物理安全性和操作系统，降低了 IT 成本
