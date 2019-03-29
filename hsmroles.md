---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM Roles
{: #ibm-cloud-hsm-roles}

This topic outlines the roles that access the {{site.data.keyword.cloud}} HSM, and the cryptographic engine within or connected to the host.  
{:shortdesc}

## Mandatory Roles
<li>HSM Security Officer (SO): responsible for initialization of the HSM, setting and changing of HSM Policies (based on the HSM's Capabilities), creation and deletion of application partitions
<li>Partition Security Officer (PO): responsible for initializing the Crypto Officer role on the partition, resetting passwords, setting and changing partition-level Policies (based on the HSM's and the partition's Capabilities)
<li>Crypto Officer (CO): responsible for initializing the Crypto User role, and for creating and modifying cryptographic objects in the HSM partition

## Optional Roles
{: #optional-roles}

<li>Auditor (Au): responsible for managing HSM audit logging, independent from other roles on the HSM
<li>Crypto User (CU): responsible for using cryptographic objects (encrypt/decrypt, sign/verify and more) in the HSM partition

## Enhanced Cryptoki Model
{: #enhanced-cryptoki-model}

The separation of roles on the SafeNet Luna Network HSM follows an enhanced Cryptoki model for the following roles:

### HSM Security Officer (SO)
{: #hsm-security-officer-so}

The HSM SO has control of the HSM within the SafeNet Luna Network HSM appliance. To access HSM SO functions, you must first be logged in as appliance admin.
In addition to all the other appliance functions, a user who has authenticated with the HSM SO credential can:
<li>Create and delete partitions
<li>Back up and restore the HSM
<li>Change HSM Policies

### Partition Security Officer (PO)
{: #partition-security-officer-po}

The Partition Security Officer has control of one or more partitions (virtual HSMs) within the SafeNet Luna Network HSM. To access Partition SO functions, you must log in using the LunaCM utility on a registered Client computer.
The Partition SO, when logged in to the partition, can:
<li>Modify partition policies
<li>Back up and restore partition contents
<li>Initialize the Crypto Officer role

### Crypto Officer (CO)
{: #crypto-officer-co}

The Crypto Officer has full Read-Write access to the partition through the LunaCM utility on a registered Client computer. The Crypto Officer partition credential allows a Client application to perform any cryptographic operation, including:
<li>Key Generation/Deletion
<li>Wrap/Unwrap
<li>Encrypt/Decrypt
<li>Sign/Verify</li>
The Crypto Officer can also initialize the optional Crypto User role.

### Crypto User (CU)
{: #cypto-user-cu}

The Crypto User is a restricted Read-only Client user. Once initialized, the authenticated Crypto User can access cryptographic materials already existing on the partition (for signing, verifying, encrypting, decrypting), but cannot manipulate those objects (no generating, deleting, or wrapping/unwrapping).
The Crypto User role is optional. If you have no security requirement for this role, it can remain uninitialized and all Client applications can access the partition using the Crypto Officer credential.
