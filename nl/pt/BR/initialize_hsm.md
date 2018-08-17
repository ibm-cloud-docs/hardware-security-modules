---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Inicializando o IBM Cloud HSM

Depois de ter acesso ao Hardware Security Module (HSM), deve-se inicializar o HSM. Talvez também seja necessário reinicializá-lo no futuro. Para inicializar o HSM, conclua as etapas a seguir.
{:shortdesc}

1. Inicialize o HSM [myLuna] lusash:.hsm init -label Customer1Prod'.
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
Resultado do Comando: 0 (Sucesso)
```
