---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM 角色
{: #ibm-cloud-hsm-roles}

此主题概述了访问 {{site.data.keyword.cloud}} HSM 的角色，以及主机中或连接到主机的加密引擎。  
{:shortdesc}

## 必需角色
<li>HSM 安全主管 (SO)：负责 HSM 的初始化、HSM 策略的设置和更改（基于 HSM 的功能）以及应用程序分区的创建和删除
<li>分区安全主管 (PO)：负责初始化分区上的加密主管角色、重置密码以及设置和更改分区级别策略（基于 HSM 和分区的功能）
<li>加密主管 (CO)：负责初始化加密用户角色，以及在 HSM 分区中创建和修改加密对象

## 可选角色
{: #optional-roles}

<li>审计员 (Au)：负责管理 HSM 审计日志记录，独立于 HSM 上的其他角色
<li>加密用户 (CU)：负责在 HSM 分区中使用加密对象（加密/解密、签名/验证等）

## 增强 Cryptoki 模型
{: #enhanced-cryptoki-model}

SafeNet Luna Network HSM 上的角色分离遵循以下角色的增强 Cryptoki 模型：

### HSM 安全主管 (SO)
{: #hsm-security-officer-so}

HSM 安全主管对 SafeNet Luna Network HSM 设备中的 HSM 具有控制权。要访问 HSM 安全主管功能，必须先以设备管理员身份登录。
除了所有其他设备功能外，已经通过 HSM 安全主管凭证进行认证的用户可以执行以下操作：
<li>创建和删除分区
<li>备份和复原 HSM
<li>更改 HSM 策略

### 分区安全主管 (PO)
{: #partition-security-officer-po}

分区安全主管对 SafeNet Luna Network HSM 中的一个或多个分区（虚拟 HSM）具有控制权。要访问分区安全主管功能，必须在已注册的客户端计算机上使用 LunaCM 实用程序登录。
登录到分区时，分区安全主管可以执行以下操作：
<li>修改分区策略
<li>备份和复原分区内容
<li>初始化加密主管角色

### 加密主管 (CO)
{: #crypto-officer-co}

加密主管通过已注册的客户端计算机上的 LunaCM 实用程序对分区具有完全读/写访问权。加密主管分区凭证允许客户机应用程序执行任何加密操作，包括：
<li>密钥生成/删除
<li>打包/解包
<li>加密/解密
<li>签名/验证</li>
加密主管还可以初始化可选加密用户角色。

### 加密用户 (CU)
{: #cypto-user-cu}

加密用户是受限的只读客户机用户。初始化之后，已认证的加密用户可以访问分区上已经存在的加密资料（例如签名、验证、加密和解密），但是无法操作这些对象（无法生成、删除或打包/解包）。
加密用户角色是可选的。如果您对此角色没有安全需求，那么它可以保持未初始化状态，并且所有客户机应用程序可以使用加密主管凭证来访问分区。
