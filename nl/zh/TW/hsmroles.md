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

本主題概述存取 {{site.data.keyword.cloud}} HSM 的角色，以及內部或連接至主機的加密引擎。  
{:shortdesc}

## 必要的角色
<li>HSM 安全性管理者 (SO)：負責起始設定 HSM、設定和變更 HSM 原則（根據 HSM 的容量）、建立和刪除應用程式分割區
<li>分割區安全性管理者 (PO)：負責起始設定分割區的「加密管理者」角色、重設密碼、設定和變更分割區層次的原則（根據 HSM 及分割區的容量）
<li>加密管理者 (CO)：負責起始設定「加密使用者」角色，以及在 HSM 分割區中建立和修改加密物件

## 選用性角色
{: #optional-roles}

<li>審核員 (Au)：負責管理 HSM 審核記載，與 HSM 的其他角色無關
<li>加密使用者 (CU)：負責在 HSM 分割區中使用加密物件（加密/解密、簽署/驗證，等等）

## 加強型 Cryptoki 模型
{: #enhanced-cryptoki-model}

SafeNet Luna Network HSM 上的角色區隔，會針對下列角色遵循加強型 Cryptoki 模型：

### HSM 安全性管理者 (SO)
{: #hsm-security-officer-so}

HSM SO 能控制 SafeNet Luna Network HSM 應用裝置內的 HSM。若要存取 HSM SO 功能，您必須先以應用裝置管理者的身分登入。除了所有其他應用裝置之外，已使用 HSM SO 認證通過鑑別的使用者還可以：
<li>建立及刪除分割區
<li>備份及還原 HSM
<li>變更 HSM 原則

### 分割區安全性管理者 (PO)
{: #partition-security-officer-po}

分割區安全性管理者可以控制 SafeNet Luna Network HSM 內的一個以上分割區（虛擬 HSM）。若要存取「分割區 SO」功能，您必須在已登錄的用戶端電腦上，使用 LunaCM 公用程式登入。分割區 SO 在登入分割區之後，可以：
<li>修改分割區原則
<li>備份及還原分割區內容
<li>起始設定「加密管理者」角色

### 加密管理者 (CO)
{: #crypto-officer-co}

「加密管理者」透過已登錄用戶端電腦上的 LunaCM 公用程式，對於分割區有完整的讀寫存取權。「加密管理者」分割區認證容許用戶端應用程式執行任何加密作業，包括：
<li>金鑰產生/刪除
<li>包裝/解除包裝
<li>加密/解密
<li>簽署/驗證</li>
「加密管理者」也可以起始設定選用性的「加密使用者」角色。

### 加密使用者 (CU)
{: #cypto-user-cu}

「加密使用者」是受限的唯讀用戶端使用者。起始設定之後，經過鑑別的「加密使用者」可以存取已經存在於分割區上的加密資料（進行簽署、驗證、加密、解密），但無法操作那些物件（無法產生、刪除或包裝/解除包裝）。「加密使用者」角色是選用性的。如果您沒有對這個角色的安全需求，可以維持不起始設定，所有用戶端應用程式可以使用「加密管理者」認證來存取分割區。
