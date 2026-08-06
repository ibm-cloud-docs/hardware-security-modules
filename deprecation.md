---

copyright:
  years: 2026
lastupdated: "2026-08-06"

keywords: HSM deprecation, hardware security module end of support, IBM Cloud HSM EOS, Utimaco migration

subcollection: hardware-security-modules

---

{{site.data.keyword.attribute-definition-list}}

# Deprecation of IBM Cloud Classic infrastructure Hardware Security Module
{: #deprecation}

{{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) is deprecated, and no new instances can be created. The service will no longer be supported by {{site.data.keyword.cloud_notm}} as of 11 August 2027. At the end-of-support date, any instances of {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) that are still running will be permanently disabled and deprovisioned.
{: shortdesc}

## Important dates
{: #deprecation-timeline}

| Stage | Date | Description |
| ---------------- | ----------------- | ------------------------------------------------------------ |
| End of marketing | 11 August 2026 | No new instances of {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) can be created or purchased. Existing instances will continue to run. |
| Migration available | 11 August 2026 | IBM clients can begin migrating to Utimaco's HSM service. IBM recommends completing your migration by 31 December 2026. |
| End of support | 11 August 2027 | You can continue to use any existing instances of {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM), but support is no longer available. Running instances are permanently disabled and deprovisioned. |
{: caption="Deprecation timeline" caption-side="bottom"}

## Deprecation details
{: #deprecation-details}

Review the following details about the {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) deprecation:

* {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) is being deprecated. No new instances can be created or purchased.
* Existing instances will continue to run until 11 August 2027, when they will be permanently disabled and deprovisioned, including any user data.
* This deprecation means that support, including updates, bug fixes, and technical support, is no longer available effective 11 August 2027.
* No support cases can be opened after 11 August 2027.
* IBM is working with Utimaco on an accelerated migration process for all clients. IBM strongly recommends completing your migration to an alternative service by 31 December 2026 to minimize operational and security risk.
* An equivalent product is available for you to start migrating to today. For more information, see [Utimaco HSM](https://utimaco.com/).

## Next steps for current users
{: #deprecation-next-steps}

You can continue to use existing instances of {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) even though the service is deprecated. However, {{site.data.keyword.IBM_notm}} will no longer provide support, including bug fixes or security updates, after 11 August 2027. IBM strongly recommends migrating to Utimaco's HSM service or another provider of your choosing as soon as possible, and completing the migration by 31 December 2026. As of 11 August 2027, all running instances will be deleted, including any user data.

If you have questions about this deprecation, you can contact {{site.data.keyword.cloud_notm}} Support until the end-of-support date on 11 August 2027.
{: note}

### Migrating to Utimaco HSM
{: #migrate-utimaco}

Utimaco's HSM service is now available as a replacement for {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM), offering equivalent functionality. IBM clients can choose from a variety of solution configurations, including Standard Live General Purpose HSM Service and Premium Live General Purpose HSM Service. Choose the option that best meets your requirements.

To begin your migration:

1. Review the available Utimaco solution configurations at [utimaco.com](https://utimaco.com){: external} to select the option that best meets your requirements.
2. Work with your IBM Cloud seller or Client Success Manager (CSM) to connect with Utimaco for migration assistance.
3. Complete your migration by 31 December 2026 to ensure a smooth transition before the 11 August 2027 end-of-support date.

### Identifying your HSM device type
{: #deprecation-device-type}

To confirm the hardware type that you have in your account:

1. Go to your account portal.
2. Under **Devices**, select **Device List**.
3. In the Device listing page, click the device name.
4. Click **Overview** of the device you selected.
5. Under **System details**, the server information is shown. The processor title indicates the server type.

Use this information to identify whether your server is affected by this end-of-support notice.

### Deleting Classic infrastructure Hardware Security Module instances and data
{: #service-delete}

Existing instances of {{site.data.keyword.cloud}} Classic infrastructure Hardware Security Module (HSM) can continue to be used until 11 August 2027. You can start deleting your service instances and associated data when you are ready by using the IBM Cloud console or the Classic Infrastructure API. This ensures that all instances and user information stored in the service are permanently deleted.

If you don't manually delete your instances and data before 11 August 2027, it will be done for you on that date.
{: note}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com){: external}.
2. From the navigation menu, go to **Classic Infrastructure** > **Devices** > **Device List**.
3. Locate your HSM device and click the device name.
4. From the **Actions** menu, select **Cancel Device**.
5. Confirm the cancellation to permanently delete the instance and associated data.

For more details about data deletion policies, see [Securing your data in Classic infrastructure Hardware Security Module](/docs/hardware-security-modules?topic=hardware-security-modules-data-security).
