---

copyright:
  years: 2014, 2024
lastupdated: "2024-05-16"

keywords: hardware security modules, HSM, partitions, labels, cryptographic, keys,

subcollection: hardware-security-modules

---

{{site.data.keyword.attribute-definition-list}}

# Creating IBM Cloud Hardware Security Module partitions
{: #creating-ibm-cloud-hsm-partitions}

Within an {{site.data.keyword.cloud}} Hardware Security Module (HSM), separate cryptographic workspaces must be initialized and designated for clients. A workspace, or *partition*, and all its contents are protected by encryption that is derived from its authentication. Only a client that presents the proper authentication can see the partition and work with its contents.
{: shortdesc}

When you create your partitions, be aware that partition names, also known as labels, must be unique in the HSM. You cannot create two partitions with the same label on one HSM. What you name your partition is the label that is seen by Public-Key Cryptographic Standards (PKCS) #11 applications.

1. Log in as the HSM Administrator with the password that is used for initializing the HSM.

   ```text
   [myLuna] lunash:>hsm login
   Please enter HSM Administrators' password:
   >**************
   hsm login successful.
   Command Result : 0 (Success)
   ```
   {: codeblock}
   
2. Create the partition.

   ```text
   [myLuna] Lunash:>partition create - partition customerPartionProd
   Ensure that you purchased licenses for at least this number of partitions: 1
   To continue, enter proceed, otherwise enter quit.
   > proceed
   Processing...
   Enter a password for the partition
   >**************
   Re-enter password to confirm:
   >**************
   Enter the cloning domain to use when you created this partition (press enter to use the default domain):
   > MyDomain
   partition create successful
   Command Result : 0 (Success)
   ```
   {: codeblock}
   
