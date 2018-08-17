---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 起始設定 IBM Cloud HSM

具有「硬體安全模組 (HSM)」存取權之後，您必須起始設定 HSM。您未來也可能需要對它重新起始設定。若要起始設定 HSM，請完成下列步驟。
{:shortdesc}

1. 起始設定 HSM [myLuna] lusash:.hsm init -label Customer1Prod'。
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
