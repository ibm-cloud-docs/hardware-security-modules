---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 建立 IBM Cloud HSM 分割區

在 {{site.data.keyword.cloud}}「硬體安全模組 (HSM)」內，必須為用戶端起始設定並指定個別的加密工作區。工作區或*分割區* 及其所有內容，都受到衍生自其鑑別的加密所保護。只有提供適當鑑別的用戶端，才能查看分割區並使用其內容。
{:shortdesc}

建立分割區時，請注意分割區名稱（也稱為標籤）在 HSM 中必須是唯一的。您不能在一個 HSM 上建立兩個具有相同標籤的分割區。您命名的分割區名稱，就是「公開金鑰加密標準 (PKCS)」#11 應用程式所看到的標籤。

1. 以 HSM 管理者身分，並使用起始設定 HSM 時所使用的密碼來進行登入。
```
[myLuna] lusash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. 建立分割區。
```
[myLuna] Lunash:>partition create - partition customerPartionProd
Please ensure that you have purchased licenses for at least this number of partitions: 1
If you are sure to continue then type proceed, otherwise type quit.
> proceed
Processing...
Please enter a password for the partition
>**************
Please re-enter password to confirm:
>**************
Please enter the cloning domain to use when creating this partition (press enter to use the default domain):
> MyDomain
partition create successful
Command Result : 0 (Success)
```
