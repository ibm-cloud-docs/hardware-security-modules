---

copyright:
  years: 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:note: .note}

# Gestión del IBM Cloud HSM
{: #managing-your-ibm-cloud-hsm}

Desde la Lista de dispositivos, puede gestionar el HSM (Hardware Security Module) de {{site.data.keyword.cloud}}, los servidores virtuales y los servidores nativos.
{:shortdesc}

En la lista de dispositivos, los servidores virtuales tienen el tipo de dispositivo *Virtual*. Los servidores nativos se indican con el tipo de dispositivo *Servidor*. Los hosts dedicados tienen el tipo de dispositivo *Host virtual dedicado*. HSM tiene un tipo de dispositivo *Security Module*.
Siga los siguientes pasos para realizar tareas de gestión para los servidores virtuales desde la lista de dispositivos en el {{site.data.keyword.slportal}}:  
1. Inicie una sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window} utilizando sus credenciales exclusivas.
2. En el menú **Dispositivos**, seleccione **Lista de dispositivos**.
3. Pulse **Acciones** para el dispositivo que desea gestionar y seleccione la tarea de gestión que desea.

## Supresión de la instancia de servidor
{: #deleting-the-server-instance}

En cualquier momento, puede suprimir el módulo de seguridad de hardware si ya no necesita la instancia y no desea que se le facture.

Para suprimir el HSM, vaya al menú y seleccione **Cancelar**.

## Apagar un HSM
{: #powering-off-an-hsm}

Para apagar el HSM, vaya al menú y seleccione Encender/Apagar. Mientras que el HSM esté apagado, se le seguirá facturando.

Si el HSM está apagado, seguirá en el estado apagado y deberá encenderlo manualmente.
{: note}
