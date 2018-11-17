---
copyright:
  years: 2014, 2018
lastupdated: "2018-11-16"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Creating IBM Cloud HSM partitions

Within an {{site.data.keyword.cloud}} Hardware Security Module (HSM), separate cryptographic workspaces must be initialized and designated for clients. A workspace, or *partition*, and all its contents are protected by encryption derived from its authentication. Only a client that presents the proper authentication is allowed to see the partition and work with its contents. 
{:shortdesc}

When creating your partitions, be aware that partition names, also known as labels, must be unique in the HSM. You cannot create two partitions with the same label on one HSM. What you name your partition is the label that is seen by Public-Key Cryptographic Standards (PKCS) #11 applications.

1. Log in as the HSM Administrator with the password used for initializing the HSM.
```
[myLuna] lunash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. Create the partition.
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
