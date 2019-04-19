---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Avvio di IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

Dopo aver eseguito l'accesso all'HSM (Hardware Security Module), devi avviarlo. Potresti inoltre doverlo riavviare in futuro. Per avviare l'HSM, completa la seguente procedura:
{:shortdesc}

1. Inizializza l'HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.
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

Fai riferimento a [LunaSH Command Reference Guide ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window} per tutti i comandi disponibili supportati nella CLI HSM.
