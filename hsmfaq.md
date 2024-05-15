---

copyright:
  years: 2014, 2024
lastupdated: "2024-05-15"

keywords: frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{{site.data.keyword.cloud}}

# FAQs: IBM Cloud Hardware Security Module
{: #faqs-ibm-cloud-hsm}

The {{site.data.keyword.cloud}} HSM offering provides dedicated, single-tenant encryption, key management, and storage "as a service" using Hardware Security Modules (HSMs).
{: shortdesc}

## What is a Hardware Security Module (HSM)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}

An HSM is hardware that processes cryptographic operations and does not allow encryption keys to leave the secure cryptographic environment. Data that is shared, stored, or in motion, is encrypted at its point of creation and you can run and maintain your own data protection policies in the cloud.

## What Hardware Security Module does {{site.data.keyword.cloud_notm}} rely on?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}

{{site.data.keyword.IBM}} uses Thales SafeNet Luna Network HSM technology for the {{site.data.keyword.cloud}} HSM 7.0 offering. This solution gives ease of access to {{site.data.keyword.cloud}} data centers around the world that you can use to solve compliance and data sovereignty challenges.

## Which version of {{site.data.keyword.cloud_notm}} Hardware Security Module did I need to order?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}

In most cases, you need to order the newest version of an HSM. With older versions, you might have compatibility issues with high availability if you have older HSMs. If you already have older versions, contact [support](/docs/get-support?topic=get-support-get-supportfaq#contactsupport) to determine which version is right for you.

## Can I migrate my existing Hardware Security Module to a new version?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}

You can't migrate your HSM. Instead, cancel your existing HSM from the **Devices** menu, and order a new version.

## Is {{site.data.keyword.cloud_notm}} Hardware Security Module FIPS certified?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}

Yes, {{site.data.keyword.cloud_notm}} HSM 7.0 is FIPS 140-2 Level 3 certified, and is designed to make sure that you receive a reliable and secure solution for the management of cryptographic assets.

## What use cases can I address with {{site.data.keyword.cloud_notm}} Hardware Security Module?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}

You can use {{site.data.keyword.cloud}} HSM to support Public Key Infrastructure (PKI), code signing, database encryption, document signing, Digital Rights Management (DRM), authentication and authorization, and transaction processing.

## How many partitions does my {{site.data.keyword.cloud_notm}} Hardware Security Module support?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}

{{site.data.keyword.cloud_notm}} HSM 7.0 supports up to 10 partitions.

## How many keys can I store with {{site.data.keyword.cloud_notm}} Hardware Security Module 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}

Key capacity is calculated by creating one partition and creating keys until the partition is full. All numbers are approximate. Capacity varies depending on specific key attributes set in the key generation template and the number of partitions.

| RSA Key size | Private keys| Key pairs |
|--------------|-------------|-----------|
|RSA-2048|12,000|9,500|
|RSA-4096|6,500|5,200|
|RSA-8192|3,300|2,700|
{: caption="Table 1. RSA key capacity" caption-side="top"}

| ECDSA Key size | Private keys| Key pairs |
|--------------|-------------|-----------|
|P-256|63,000|37,500|
|P-384|58,000|33,000|
|P-521|48,000|27,000|
|BrainpoolP512r1|48,000|27,000|
|P-521|48,000|27,000|
{: caption="Table 2. ECDSA key capacity" caption-side="top"}

| Symmetrical Key size | Keys|
|--------------|-------------|
|AES128|126,000|
|AES256|112,000|
|DES|140,000|
|3DES|123,000|
{: caption="Table 3. Symmetrical key capacity" caption-side="top"}

## How can I determine my {{site.data.keyword.cloud_notm}} Hardware Security Model version?
{: how-can-i-determine-my-hsm-version}
{: faq}

Use the following steps to determine your HSM version. 

1. From the IBM Cloud console, go to your **Resource list**.
2. From your Resource list, click **Devices**.
3. Under **Server details**, the model type is listed as **Luna Network HSM-SA7000** or **Luna Network HSM-A750**.

## Can I configure high availability for my {{site.data.keyword.cloud_notm}} Hardware Security Module?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}

Yes, to configure high availability across partitions of the {{site.data.keyword.cloud_notm}} HSM by using secrets, see the Installation Guide for your HSM version. [My Products](https://supportportal.gemalto.com/csm?id=csm_my_products){: external}. A login for the Thales Support Portal is required.

## How can I back up my {{site.data.keyword.cloud_notm}} Hardware Security Module configuration?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}

To back up your {{site.data.keyword.cloud_notm}} HSM configuration, see the Appliance Administration Guide for your HSM version. You can find the appropriate Appliance Administration Guide from the [My Products](https://supportportal.gemalto.com/csm?id=csm_my_products){: external} page on the Thales Portal.
