---

copyright:
  years: 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:note: .note}

# 管理 IBM Cloud HSM
{: #managing-your-ibm-cloud-hsm}

通过“设备列表”，可以管理 {{site.data.keyword.cloud}} Hardware Security Module (HSM)、虚拟服务器和裸机服务器。
{:shortdesc}

在“设备列表”中，虚拟服务器的设备类型为*虚拟*。裸机服务器的所示设备类型为*服务器*。专用主机的设备类型为*专用虚拟主机*。HSM 的设备类型为*安全模块*。
要在 {{site.data.keyword.slportal}} 的“设备列表”中针对虚拟服务器执行管理任务，请完成以下步骤：  
1. 使用您的唯一凭证来登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){: new_window}。
2. 从**设备**菜单中，选择**设备列表**。
3. 针对要管理的设备，单击**操作**，然后选择所需的管理任务。

## 删除服务器实例
{: #deleting-the-server-instance}

如果您不再需要实例，并且不想再付费，您随时可以删除硬件安全模块。

要删除 HSM，请转至相应菜单，并选择**取消**。

## 关闭 HSM 的电源
{: #powering-off-an-hsm}

要关闭 HSM 的电源，请转至相应菜单，并选择“打开/关闭电源”。HSM 电源关闭期间，仍会对您计费。

关闭 HSM 电源后，HSM 会保持电源关闭状态，您必须手动打开其电源。
{: note}
