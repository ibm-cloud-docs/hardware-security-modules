---

copyright:
  years: 2014, 2021
lastupdated: "2021-02-10"

keywords: hardware security modules, HSM, frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}

# FAQs: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

The {{site.data.keyword.cloud}} HSM offering provides dedicated, single-tenant encryption, key management, and storage "as a service" using Hardware Security Modules (HSMs).
{: shortdesc}

## What is a Hardware Security Module (HSM)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}

An HSM is a piece of hardware that processes cryptographic operations and does not allow encryption keys to leave the secure cryptographic environment. Data that is shared, stored, or in motion, is encrypted at its point of creation and you can run and maintain your own data protection policies in the cloud.

## What HSM does {{site.data.keyword.cloud_notm}} rely on?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}

{{site.data.keyword.IBM}} leverages Thales SafeNet Luna Network HSM technology for Cloud HSM 6.0 and 7.0 offerings. This solution gives use ease of access to 60 {{site.data.keyword.cloud}} data centers around the world that you can use to solve their compliance and data sovereignty challenges.

## Which version of {{site.data.keyword.cloud_notm}} HSM should I order?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}

In most cases, you need to order the newest version of an HSM. With older versions, you might have compatibility issues with high availability if you have older HSMs. If you already have older versions, contact Support to determine which version is right for you.

## Can I migrate my existing HSM to a new version?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}

Your HSM can't be migrated. Instead, cancel your existing HSM from the **Devices** menu, and order a new version.

## Is {{site.data.keyword.cloud_notm}} HSM FIPS certified?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}

Yes, {{site.data.keyword.cloud_notm}} HSM 7.0 is FIPS 140-2 Level 3 certified, and is designed to make sure that enterprises receive a reliable and secure solution for the management of their cryptographic assets. IBM Cloud HSM 6.0 is FIPS 140-2 Level 2 certified for Public Key Infrastructure (PKI), digital signatures, and cryptographic key storage.

## What use cases can I address with {{site.data.keyword.cloud_notm}} HSM?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}

You can use the HSM service to support Public Key Infrastructure (PKI), code signing, database encryption, document signing, Digital Rights Management (DRM), authentication and authorization, and transaction processing.

## How many partitions will my {{site.data.keyword.cloud_notm}} HSM support?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}

{{site.data.keyword.cloud_notm}} HSM 6.0 and 7.0 support up to 10 partitions.

## How many keys can be stored with {{site.data.keyword.cloud_notm}} HSM 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}

Key capacity is calculated by creating one partition and creating keys until the partition is full. All numbers are approximate. Capacity varies depending on specific key attributes set in the key generation template and number of partitions.

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

## How can I determine my {{site.data.keyword.cloud_notm}} HSM version?
{: how-can-i-determine-my-hsm-version}
{: faq}

Use the following steps to determine your HSM version. 

1. From the [IBM Cloud Dashboard](https://test.cloud.ibm.com/){: external}, go to the **Resource list** by clicking the ![Resource list icon](../../images/Resource-list.png) symbol on the white sidebar to the left.
2. From the Resource list page, expand the Devices dropdown list by clicking the arrow to the left of Devices.
3. Under Server Details, the Model type is listed as **Luna Network HSM-SA7000** or **Luna Network HSM-A750**.

## Can I configure high availability for my {{site.data.keyword.cloud_notm}} HSM?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}

Yes, to configure high availability across partitions of the {{site.data.keyword.cloud_notm}} HSM by using secrets, see the Installation Guide for your HSM version. [My Products](https://supportportal.gemalto.com/csm?id=csm_my_products){: external}. Log in to the Thales Support Portal is required.

## How can I back up my {{site.data.keyword.cloud_notm}} HSM configuration?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}

To backup your {{site.data.keyword.cloud_notm}} HSM configuration, see the Appliance Administration Guide for your HSM version. The appropriate Appliance Administration Guide can be found from the [My Products](https://supportportal.gemalto.com/csm?id=csm_my_products){: external} page on the Thales Portal.
