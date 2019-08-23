---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# 初始化 IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

您有权访问 Hardware Security Module (HSM) 之后，必须对 HSM 进行初始化。此外，未来还可能需要对 HSM 进行重新初始化。要初始化 HSM，请完成以下步骤。
{:shortdesc}

1. 初始化 HSM `[myLuna] lusash:.hsm init -label Customer1Prod`。
```
Please enter a password for the HSM Administrator:
>**************
Please re-enter password to confirm:
>**************
Please enter the cloning domain to use for initializing this HSM (press to use the default domain):
>MyDomain
CAUTION: Are you sure you wish to re-initialize this HSM?
All partitions and data will be erased.
Type proceed to initialize the HSM, or type quite to quit now.
>proceed
hsm init successful.
Command Result : 0 (Success)
```

请参阅 [LunaSH Command Reference Guide ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}，以获取 HSM CLI 中支持的所有可用命令。
