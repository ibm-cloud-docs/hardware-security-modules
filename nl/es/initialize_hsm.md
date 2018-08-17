---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Inicialización del IBM Cloud HSM

Una vez que tenga acceso al HSM (Hardware Security Module), debe inicializar el HSM. También es posible que necesite reinicializarlo en el futuro. Para inicializar el HSM, complete los pasos siguientes. 
{:shortdesc}

1. Inicialice el HSM [myLuna] lusash:.hsm init -label Customer1Prod'.
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
