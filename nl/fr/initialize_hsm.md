---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Initialisation du module IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

Une fois que vous accès au module HSM (Hardware Security Module), vous devez l'initialiser. Vous aurez peut-être à la réinitialiser plus tard. Pour initialiser le module HSM, procédez comme suit.
{:shortdesc}

1. Initialisez le module HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.
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

Pour en savoir plus sur les commandes disponibles prises en charge par l'interface CLI de HSM, voir le document [LunaSH Command Reference Guide ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}. 
