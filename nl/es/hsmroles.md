---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Roles de IBM Cloud HSM
{: #ibm-cloud-hsm-roles}

En este tema se describen los roles que acceden a {{site.data.keyword.cloud}} HSM y el motor de criptografía del host o conectado al mismo.  
{:shortdesc}

## Roles obligatorios
<li>Agente de seguridad (SO) de HSM: responsable de inicializar el HSM, definir y cambiar las políticas de HSM (en función de las prestaciones del HSM) y de crear y suprimir particiones de la aplicación
<li>Agente de seguridad de la partición (PO): responsable de inicializar el rol de Agente de criptografía en la partición, restablecer contraseñas y definir y cambiar políticas a nivel de partición (en función de las prestaciones del HSM y de la partición)
<li>Agente de criptografía (CO): responsable de inicializar el rol de Usuario de criptografía y de crear y modificar objetos criptográficos en la partición del HSM

## Roles opcionales
{: #optional-roles}

<li>Auditor (Au): responsable de gestionar el registro de auditoría de HSM, independiente de otros roles del HSM
<li>Usuario de criptografía (CU): responsable de utilizar objetos criptográficos (cifrar/descifrar, firmar/verificar y más) en la partición del HSM

## Modelo Cryptoki mejorado
{: #enhanced-cryptoki-model}

La separación de roles de SafeNet Luna Network HSM sigue un modelo Cryptoki mejorado para los siguientes roles:

### Agente de seguridad (SO) de HSM
{: #hsm-security-officer-so}

El SO de HSM tiene el control del HSM dentro del dispositivo SafeNet Luna Network HSM. Para acceder a las funciones del SO de HSM, primero debe iniciar una sesión como administrador del dispositivo.
Además de todas las demás funciones del dispositivo, un usuario autenticado con la credencial de SO de HSM puede:
<li>Crear y suprimir particiones
<li>Hacer copia de seguridad y restaurar el HSM
<li>Cambiar políticas del HSM

### Agente de seguridad de la partición (PO)
{: #partition-security-officer-po}

El Agente de seguridad de la partición tiene el control de una o varias particiones (HSM virtuales) dentro de dispositivo SafeNet Luna Network HSM. Para acceder a las funciones del SO de partición, debe iniciar una sesión mediante el programa de utilidad LunaCM en un sistema cliente registrado.
El SO de la partición, cuando ha iniciado una sesión en la partición, puede:
<li>Modificar políticas de partición
<li>Hacer copia de seguridad y restaurar el contenido de la partición
<li>Inicializar el rol de Agente de criptografía

### Agente de criptografía (CO)
{: #crypto-officer-co}

El Agente de criptografía tiene acceso completo de lectura y escritura sobre la partición a través del programa de utilidad LunaCM en un sistema cliente registrado. La credencial de partición del Agente de criptografía permite a una aplicación cliente realizar cualquier operación criptográfica, como por ejemplo:
<li>Generar y suprimir claves
<li>Comprimir y descomprimir
<li>Cifrar y descifrar
<li>Firmar y verificar</li>
El Agente de criptografía también puede inicializar el rol opcional Usuario de criptografía.

### Usuario de criptografía (CU)
{: #cypto-user-cu}

El Usuario de criptografía es un usuario cliente restringido de solo lectura. Una vez inicializado, el Usuario de criptografía autenticado puede acceder al material criptográfico existente en la partición (para firmar, verificar, cifrar, descifrar), pero no puede manipular estos objetos (no puede generar, suprimir, comprimir ni descomprimir).
El rol Usuario de criptografía es opcional. Si no tiene ningún requisito de seguridad para este rol, puede permanecer sin inicializar y todas las aplicaciones cliente pueden acceder a la partición con la credencial de Agente de criptografía.
