---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Inicializando o IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

Depois de ter acesso ao Hardware Security Module (HSM), deve-se inicializar o HSM. Talvez também seja necessário reinicializá-lo no futuro. Para inicializar o HSM, conclua as etapas a seguir.
{:shortdesc}

1. Inicialize o HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.
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

Consulte o [Guia de referência de comando do LunaSH ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window} para obter os comandos disponíveis suportados na CLI do HSM.
