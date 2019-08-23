---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM の初期化
{: #initializing-the-ibm-cloud-hsm}

Hardware Security Module (HSM) にアクセスした後に、HSM を初期化する必要があります。 将来、再初期化する必要が生じることもあります。 HSM を初期化するには、以下の手順を実行します。
{:shortdesc}

1. HSM を初期化します。`[myLuna] lusash:.hsm init -label Customer1Prod`
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

HSM CLI でサポートされるすべての使用可能なコマンドについては、[「LunaSH Command Reference Guide」![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}を参照してください。
