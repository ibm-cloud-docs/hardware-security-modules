---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Initializing the IBM Cloud HSM

After you have access to the Hardware Security Module (HSM), you must initialize the HSM. You might also need to reinitialize it in the future. To initialize the HSM, complete the following steps. 
{:shortdesc}

1. Initialize the HSM [myLuna] lusash:.hsm init -label Customer1Prod'.
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
