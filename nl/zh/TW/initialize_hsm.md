---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 起始設定 IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

具有 Hardware Security Module (HSM) 存取權之後，您必須起始設定 HSM。您未來也可能需要對它重新起始設定。若要起始設定 HSM，請完成下列步驟。
{:shortdesc}

1. 起始設定 HSM `[myLuna] lusash:.hsm init -label Customer1Prod`。
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

如需 HSM CLI 中支援的所有可用指令，請參閱 [LunaSH Command Reference Guide![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}。
