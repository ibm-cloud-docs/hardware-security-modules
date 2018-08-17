---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 初始化 IBM Cloud HSM

您有权访问硬件安全模块 (HSM) 之后，必须对 HSM 进行初始化。此外，未来还可能需要对 HSM 进行重新初始化。要初始化 HSM，请完成以下步骤。
{:shortdesc}

1. 初始化 HSM：[myLuna] lusash:.hsm init -label Customer1Prod'。
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
