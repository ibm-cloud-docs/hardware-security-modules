---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Inicialización del IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

Una vez que tenga acceso al HSM (Hardware Security Module), debe inicializar el HSM. También es posible que necesite reinicializarlo en el futuro. Para inicializar el HSM, complete los pasos siguientes.
{:shortdesc}

1. Inicialice el HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.
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

Consulte la [Guía de referencia de los mandatos LunaSH ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window} para ver todos los mandatos disponibles admitidos en la CLI de HSM.
