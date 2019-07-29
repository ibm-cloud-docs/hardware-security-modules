---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-26"

keywords: hardware security modules, HSM, provisioning HSM, keys

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Provisioning IBM Cloud HSM
{: #provisioning-ibm-cloud-hsm}

## Before you begin
* Navigate to your console's device menu. For more information, see [Navigating to devices](/docs/infrastructure/hardware-security-modules?topic=virtual-servers-navigating-devices).
* Ensure you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission) and [Managing device access](/docs/vsi?topic=virtual-servers-managing-device-access).

To provision your {{site.data.keyword.cloud}} HSM through the {{site.data.keyword.cloud_notm}} catalog, complete the following steps.
{:shortdesc}

1. Click the **Security and Identity** menu and select the **Cloud HSM** tile.
2. Click **Create**.
3. Select the following:

| Field | Value |
| --- | --- |
| **Billing** | Select **Hourly** or **Monthly** based on how you're using the IBM Cloud HSM. |
| **Location** | Choose the data center where your Cloud HSM is located. Available data centers are under **North America**, **Europe**, and **Asia-Pacific**. |
| **Hardware Security Module** | Select the appropriate Cloud HSM model. The latest model is recommended unless you have existing HSMs in your environment. |
{: caption="Table 1. HSM options" caption-side="top"}   

4. After you review your order summary, click the **Third-Party Service Agreements** check box.
5. Click **Provision**.
