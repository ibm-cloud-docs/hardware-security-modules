---
copyright:
  years: 2014, 2018
lastupdated: "2018-11-16"

subcollection: hardware-security-modules
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQs: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

The {{site.data.keyword.cloud}} HSM offering provides dedicated, single-tenant encryption, key management, and storage "as a service" using Hardware Security Modules (HSMs).
{:shortdesc}

## Which version of IBM Cloud HSM should I order?
{:faq}

In most cases, you should always order the newest version of HSM. Some users with older versions might have compatibility issues with high availability if they have existing older HSMs. If you already have older versions, contact Support to determine which version is right for you.

## Can I migrate my existing HSM to a new version?
{:faq}

Your HSM can't be migrated. Instead, cancel your existing HSM from the **Devices** menu, and order a new version.

## What is a Hardware Security Module (HSM)?
{:faq}

An HSM is a piece of hardware which processes cryptographic operations and does not allow encryption keys to leave the secure cryptographic environment. Data, shared, stored or in motion, is encrypted at its point of creation and companies can execute and maintain their own data protection policies in the cloud. 

## What HSM does IBM Cloud rely on?
{:faq}

IBM leverages SafeNet Luna Network HSM technology from Gemalto for IBM Cloud HSM 7.0. This solution gives customers ease of access to 60 IBM data centers around the world that they can use to solve their compliance and data sovereignty challenges. 

## Is IBM Cloud HSM FIPS certified? 
{:faq}

Yes, IBM Cloud HSM 7.0 is FIPS 140-2 Level 3 certified, and is designed to make sure that enterprises receive a reliable and secure solution for the management of their cryptographic assets. IBM Cloud HSM 6.0 is FIPS 140-2 Level 2 certified for PKI, digital signatures, and cryptographic key storage. 

## What use cases can I address with IBM Cloud HSM?
{:faq}

You can use the HSM service to support a variety of use cases and applications such as Public Key Infrastructure (PKI), code signing, database encryption, document signing, Digital Rights Management (DRM), authentication and authorization, and transaction processing.
