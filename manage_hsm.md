---

copyright:
  years: 2020
lastupdated: "2020-05-15"

keywords: hardware security modules, HSM, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:note: .note}

# Managing your IBM Cloud HSM
{: #managing-your-ibm-cloud-hsm}

From the Device List, you can manage your {{site.data.keyword.cloud}} Hardware Security Module (HSM), virtual servers, and bare metal servers.
{:shortdesc}

## Before you begin
{: #before-you-begin-manage}

* Navigate to your console's device menu. For more information, see [Navigating to devices](/docs/virtual-servers?topic=virtual-servers-navigating-devices).
* Make sure that you have any necessary account permissions and device access. Only the account owner, or a user with the **Manage Users** classic infrastructure permission, can adjust the permissions.

For more information about permissions, see [Classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission) and [Managing device access](/docs/vsi?topic=virtual-servers-managing-device-access).

In the device list, virtual servers have a device type of *Virtual*. Bare metal servers are indicated with the device type of *Server*. Dedicated hosts have a device type of *Dedicated Virtual Host*. HSM has a device type *Security Module*.
Complete the following steps to perform management tasks for your virtual servers from the Device List in the {{site.data.keyword.slportal}}:  

Click **Actions** for the device that you want to manage and select the wanted management task.

## Deleting the server instance
{: #deleting-the-server-instance}

At any time, you can delete your hardware security module if you no longer need the instance and don't want to be charged.

To delete the HSM, go to the menu and select **Cancel**.

## Powering off an HSM
{: #powering-off-an-hsm}

To power off the HSM, go to the menu and select **Power On/Off**. 

While the HSM is powered off, you are still billed.
{: note}

If the HSM is powered off, it remains in the power off state and you must manually power it on.
{: note}
