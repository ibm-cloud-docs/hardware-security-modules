---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM の初期化

Hardware Security Module (HSM) にアクセスした後に、HSM を初期化する必要があります。将来、再初期化する必要が生じることもあります。HSM を初期化するには、以下の手順を実行します。
{:shortdesc}

1. HSM を [myLuna] lusash:.hsm init -label Customer1Prod' で初期化します。
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
