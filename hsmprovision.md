---

copyright:
  years: 2014, 2021
lastupdated: "2020-05-15"

keywords: hardware security modules, HSM, provisioning HSM, keys

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Provisioning IBM Cloud HSM
{: #provisioning-ibm-cloud-hsm}

## Before you begin
{: #before-you-begin-provision}

* Go to your console's device menu. For more information, see [Navigating to devices](/docs/virtual-servers?topic=virtual-servers-navigating-devices).
* Make sure that you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/account?topic=account-infrapermission#infrapermission) and [Managing device access](/docs/virtual-servers?topic=virtual-servers-managing-device-access).

To provision your {{site.data.keyword.cloud}} HSM through the {{site.data.keyword.cloud_notm}} catalog, complete the following steps.
{:shortdesc}

1. Click the **Security and Identity** menu and select the **Cloud HSM** tile.
2. Select **Create**.
3. Select the following options:

| Field | Value |
| --- | --- |
| **Billing** | Select **Hourly** or **Monthly** based on how you're using the IBM Cloud HSM. |
| **Location** | Choose the data center where your Cloud HSM is located. Available data centers are in **North America**, **Europe**, and **Asia-Pacific**. |
| **Hardware Security Module** | Select the appropriate Cloud HSM model. The latest model is recommended unless you have existing HSMs in your environment. |
{: caption="Table 1. HSM options" caption-side="top"}   

4. After you review your order summary, click the **Third-Party Service Agreements** checkbox.
5. Click **Provision**.
