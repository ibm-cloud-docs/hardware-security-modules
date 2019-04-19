---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, partitions, labels, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 创建 IBM Cloud HSM 分区
{: #creating-ibm-cloud-hsm-partitions}

在 {{site.data.keyword.cloud}} Hardware Security Module (HSM) 中，必须初始化独立的加密工作空间并为客户机指定相应的加密工作空间。工作空间（即*分区*）及其所有内容都通过从其认证派生的加密进行保护。只允许提供相应认证的客户机查看分区并使用其内容。
{:shortdesc}

创建分区时，请注意分区名称（也称为“标签”）在 HSM 中必须唯一。不能在一个 HSM 上使用同一标签创建两个分区。命名的分区名称是公用密钥密码术标准 (PKCS) #11 应用程序看到的标签。

1. 使用用于初始化 HSM 的密码以 HSM 管理员身份登录。
```
[myLuna] lunash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. 创建分区。
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
