---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQs: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

The {{site.data.keyword.cloud}} HSM offering provides dedicated, single-tenant encryption, key management, and storage "as a service" using Hardware Security Modules (HSMs).
{:shortdesc}

## What is a Hardware Security Module (HSM)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
An HSM is a piece of hardware which processes cryptographic operations and does not allow encryption keys to leave the secure cryptographic environment. Data, shared, stored or in motion, is encrypted at its point of creation and companies can execute and maintain their own data protection policies in the cloud.

## What HSM does {{site.data.keyword.cloud_notm}} rely on?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} leverages Gemalto SafeNet Luna Network HSM technology for Cloud HSM 6.0 and 7.0 offerings. This solution gives customers ease of access to 60 {{site.data.keyword.cloud_notm}} data centers around the world that they can use to solve their compliance and data sovereignty challenges.

## Which version of {{site.data.keyword.cloud_notm}} HSM should I order?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
In most cases, you should always order the newest version of an HSM. Some users with older versions might have compatibility issues with high availability if they have existing older HSMs. If you already have older versions, contact Support to determine which version is right for you.

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
You can use the HSM service to support a variety of use cases and applications such as Public Key Infrastructure (PKI), code signing, database encryption, document signing, Digital Rights Management (DRM), authentication and authorization, and transaction processing.

## How many partitions will my {{site.data.keyword.cloud_notm}} HSM support?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 and 7.0 support up to 10 partitions.

## How many keys can be stored with {{site.data.keyword.cloud_notm}} HSM 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
Key capacity is calculated by creating one partition and creating keys until the partition is full.
All numbers are approximate. Capacity varies depending on specific key attributes set in the key generation template and number of partitions.
<table>
<th>RSA Key size
</th>
<th>Private keys</th>
<th>Key pairs</th>
<tr><td>RSA-2048</td>
<td>12,000</td>
<td>9,500</td></tr>
<tr><td>RSA-4096</td>
<td>6,500</td>
<td>5,200</td></tr>
<tr><td>RSA-8192</td>
<td>3,300</td>
<td>2,700</td></tr>

<th>ECDSA Key size
</th>
<th>Private keys</th>
<th>Key pairs</th>
<tr><td>P-256</td>
<td>63,000</td>
<td>37,500</td></tr>
<tr><td>P-384</td>
<td>58,000</td>
<td>33,000</td></tr>
<tr><td>P-521</td>
<td>48,000</td>
<td>27,000</td></tr>
<tr><td>BrainpoolP512r1</td>
<td>48,000</td>
<td>27,000</td></tr>

<th>Symmetrical Key size
</th>
<th colspan="2">Keys</th>

<tr><td>AES128</td>
<td colspan="2">126,000</td>
</tr>
<tr><td>AES256</td>
<td colspan="2">112,000</td>
</tr>
<tr><td>DES</td>
<td colspan="2">140,000</td>

</tr>
<tr><td>3DES</td>
<td colspan="2">123,000</td>
</tr>
</table>

## Can I configure high availability for my {{site.data.keyword.cloud_notm}} HSM?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Yes, to configure high availability across partitions of the {{site.data.keyword.cloud_notm}} HSM using secrets, see the [SafeNet Luna Network HSM 7.2 Installation Guide ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. Log in to the Gemalto Support Portal is required.

## How can I back up my {{site.data.keyword.cloud_notm}} HSM configuration?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
To backup your {{site.data.keyword.cloud_notm}} HSM configuration, see chapter 6 of the [Appliance Administration Guide ![External link icon](../../icons/launch-glyph.svg "External link icon")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (page 66).
