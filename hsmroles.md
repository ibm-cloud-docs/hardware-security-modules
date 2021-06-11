---

copyright:
  years: 2014, 2021
lastupdated: "2021-06-11"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM Roles
{: #ibm-cloud-hsm-roles}

The following sections outline the roles that access the {{site.data.keyword.cloud}} HSM and the cryptographic engine within or connected to the host.  
{:shortdesc}

## Mandatory roles
{: #mandatory-roles}

The following roles are mandatory if you want to access the {{site.data.keyword.cloud}} HSM.

* **HSM Security Officer (SO)** is responsible for initialization of the HSM, setting and changing of HSM policies and creating and deleting application partitions
* **Partition Security Officer (PO)** is responsible for initializing the Crypto Officer role on the partition, resetting passwords, setting and changing partition-level policies
* **Crypto Officer (CO)** is responsible for initializing the Crypto User role, and for creating and modifying cryptographic objects in the HSM partition

## Optional Roles
{: #optional-roles}

The following roles are optional if you want to access the {{site.data.keyword.cloud}} HSM.

* **Auditor (Au)** is responsible for managing HSM audit logging, independent from other roles on the HSM
* **Crypto User (CU)** is responsible for using cryptographic objects (encrypt, decrypt, sign, verify, and more) in the HSM partition

## Enhanced Cryptoki Model
{: #enhanced-cryptoki-model}

The separation of roles on the SafeNet Luna Network HSM follows an enhanced Cryptoki model for the following roles:

### HSM Security Officer (SO)
{: #hsm-security-officer-so}

The HSM SO has control of the HSM within the SafeNet Luna Network HSM appliance. To access HSM SO functions, you must first log in as appliance admin.

In addition to all the other appliance functions, a user who is authenticated with the HSM SO credential can do the following actions:

* Create and delete partitions
* Back up and restore the HSM
* Change HSM policies

### Partition Security Officer (PO)
{: #partition-security-officer-po}

The Partition Security Officer has control of one or more partitions (virtual HSMs) within the SafeNet Luna Network HSM. To access Partition SO functions, you must log in by using the LunaCM utility on a registered client computer.
The Partition SO, when logged in to the partition, can do the following actions:

* Modify partition policies
* Back up and restore partition contents
* Initialize the Crypto Officer role

### Crypto Officer (CO)
{: #crypto-officer-co}

The Crypto Officer has full read/write access to the partition through the LunaCM utility on a registered client computer. The Crypto Officer partition credential allows a client application to perform any cryptographic operation, including the following operations:

* Create and delete keys
* Wrap and unwrap
* Encrypt and decrypt
* Sign and verify
* The Crypto Officer can also initialize the optional Crypto User role.

### Crypto User (CU)
{: #cypto-user-cu}

The Crypto User is a restricted read-only client user. After initialization, the authenticated Crypto User can access cryptographic materials that exist on the partition, but can't manipulate those objects.

The Crypto User role is optional. If you don't have security requirement for this role, the CU role can remain uninitialized and all client applications can access the partition by using the Crypto Officer credential.
