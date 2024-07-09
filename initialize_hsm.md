---

copyright:
  years: 2014, 2024
lastupdated: "2024-07-09"


keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{{site.data.keyword.attribute-definition-list}}

# Initializing the IBM Cloud Hardware Security Module
{: #initializing-the-ibm-cloud-hsm}

After you have access to the Hardware Security Module (HSM), you must initialize the HSM. You might also need to reinitialize it in the future. To initialize the HSM, complete the following steps.
{: shortdesc}

Initialize the HSM `[myLuna] lusash:.hsm init -label Customer1Prod`.

The HSM admin user ID that you use to access the appliance is different from the admin user ID that you use to run commands on the appliance.
{: note}


   ```text
   Enter a password for the HSM Administrator:
   >**************
   Reenter password to confirm:
   >**************
   Enter the cloning domain to use for initializing this HSM (press to use the default domain):
   >MyDomain
   CAUTION: Are you sure that you want to reinitialize this HSM?
   All partitions and data are erased.
   Type proceed to initialize the HSM, or type quite to quit now.
   >proceed
   hsm init successful.
   Command Result : 0 (Success)
   ```
   {: codeblock}

See the Command Reference Guide for your Luna HSM version to access all available commands supported in the HSM CLI.
To access the appropriate document, use the following steps.

## Determining your HSM version
{: #determine-hsm-version}

Use the following steps to determine your HSM version.

1. From your {{site.data.keyword.cloud}} console, click **Resource list**.
2. From your Resource list, click **Devices** 
3. Under **Server details**, the model type is listed as **Luna Network HSM-SA7000** or **Luna Network HSM-A750**.

## Going to the Command Reference Guide
{: #going-to-command-reference-guide}

1. Go to the [Luna Network HSM Product Documentation](https://thalesdocs.com/gphsm/Content/luna/usb/luna_usb_releases.htm){: external}.
2. Go to your HSM version.
   - If your product is Luna Network HSM-SA7000, select **Luna SA 5** from the Active Products menu.
   - If your product is Luna Network HSM-A750, select **Luna Network HSM 7** from the Active Products menu.
3. Select **User documentation**.
4. Under **Tools and utilities**, select **Luna SH Command Reference** to open the Command Reference Guide.
