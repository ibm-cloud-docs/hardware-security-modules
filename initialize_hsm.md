---
copyright:
  years: 1994, 2018
lastupdated: "2018-02-01"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Initializing the IBM Cloud HSM

The following steps outline how to initialize Hardware Security Modules (HSMs) 
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
