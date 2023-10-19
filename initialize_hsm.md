---

copyright:
  years: 2014, 2021

lastupdated: "2023-10-19"


keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:note: .note}
{:codeblock: .codeblock}

# Initializing the IBM Cloud HSM
{: #initializing-the-ibm-cloud-hsm}

After you have access to the Hardware Security Module (HSM), you must initialize the HSM. You might also need to reinitialize it in the future. To initialize the HSM, complete the following steps.
{: shortdesc}

Initialize the HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.

The HSM admin userID that you use to access the appliance is different from the admin userID that you use to run commands on the appliance.
{: note}


   ```text
   Please enter a password for the HSM Administrator:
   >**************
   Please re-enter password to confirm:
   >**************
   Please enter the cloning domain to use for initializing this HSM (press to use the default domain):
   >MyDomain
   CAUTION: Are you sure you wish to re-initialize this HSM?
   All partitions and data will be erased.
   Type proceed to initialize the HSM, or type quite to quit now.
   >proceed
   hsm init successful.
   Command Result : 0 (Success)
   ```

See the Command Reference Guide for your Luna HSM version to access all available commands supported in the HSM CLI.
To access the appropriate document, folow the following steps.

## Determine your HSM version.
{: #determine-hsm-version}

Use the following steps to determine your HSM version. 
1. From theIBM Cloud Dashboard, navigate to the **resource list** by clicking the ![Resource list icon](../../images/Resource-list.png) symbol on the white sidebar to the left.
2. Once on the Resource list page, expand the Devices dropdown list by clicking the arrow to the left of Devices.
3. Under Server Details, the Model type will be listed as **Luna Network HSM-SA7000** or **Luna Network HSM-A750**.

## Going to the Command Reference Guide

1. Go to the [Luna Network HSM Product Documentation](https://thalesdocs.com/gphsm/Content/luna/usb/luna_usb_releases.htm){: external} page.
2. Go to your HSM version.
   - If your product is Luna Network HSM-SA7000, select **Luna SA 5** from the Active Products menu.
   - If your product is Luna Network HSM-A750, select **Luna Network HSM 7** from the Active Products menu.
3. Select **User Documentation**.
4. Under **Tools and Utilities**, select **Luna SH Command Reference** to open the Command Reference Guide.
