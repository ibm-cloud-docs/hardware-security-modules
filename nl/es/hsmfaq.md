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

# Preguntas frecuentes: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

La oferta de {{site.data.keyword.cloud}} HSM proporciona cifrado dedicado de un solo arrendatario, gestión de claves y almacenamiento "como servicio" utilizando HSM (Hardware Security Modules).
{:shortdesc}

## ¿Qué es un HSM (Hardware Security Module)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
Un HSM es una parte de hardware que procesa las operaciones criptográficas y no permite que las claves de cifrado dejen el entorno criptográfico seguro. Los datos, compartidos, almacenados o en movimiento, están cifrados en este punto de creación y las empresas pueden ejecutar y mantener sus propias políticas de protección de datos en la nube.

## ¿En qué HSM se basa {{site.data.keyword.cloud_notm}}?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} aprovecha la tecnología Gemalto SafeNet Luna Network HSM para las ofertas Cloud HSM 6.0 y 7.0. Esta solución facilita a los clientes el acceso a 60 centros de datos de {{site.data.keyword.cloud_notm}} en todo el mundo que pueden utilizar para resolver los retos de conformidad y de soberanía de datos.

## ¿Qué versión de {{site.data.keyword.cloud_notm}} HSM debo solicitar?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
En la mayoría de los casos, siempre debería solicitar la versión más reciente de un HSM. Algunos usuarios con versiones más antiguas pueden tener problemas de compatibilidad con alta disponibilidad si tienen HSM más antiguos existentes. Si ya tiene versiones más antiguas, póngase en contacto con el Soporte para determinar qué versión es la correcta para usted.

## ¿Puedo migrar mi HSM existente a una versión nueva?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
El HSM no se puede migrar. En su lugar, cancele el HSM existente desde el menú **Dispositivos** y solicite una versión nueva.

## ¿Tiene {{site.data.keyword.cloud_notm}} HSM certificación FIPS?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
Sí, {{site.data.keyword.cloud_notm}} HSM 7.0 tiene la certificación FIPS 140-2 Nivel 3 y está diseñado para garantizar que las empresas reciban una solución fiable y segura para la gestión de sus activos criptográficos. IBM Cloud HSM 6.0 tiene la certificación FIPS 140-2 Nivel 2 para la infraestructura de clave pública (PKI), las firmas digitales y el almacenamiento de claves criptográficas.

## ¿Qué casos de uso puedo solucionar con {{site.data.keyword.cloud_notm}} HSM?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
Puede utilizar el servicio de HSM para dar soporte a una variedad de casos de uso y aplicaciones como infraestructura de claves públicas (PKI), firmado de código, cifrado de base de datos, firmado de documentos, gestión de derechos digitales (DRM), autenticación y autorización y proceso de transacción.

## ¿Cuántas particiones admite mi solución {{site.data.keyword.cloud_notm}} HSM?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 y 7.0 admiten un máximo de 10 particiones.

## ¿Cuántas claves se pueden almacenar con {{site.data.keyword.cloud_notm}} HSM 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
La capacidad de claves se calcula creando una partición y creando claves hasta que la partición se llena.
Todos los números son aproximados. La capacidad varía en función de los atributos específicos de claves definidos en la plantilla de generación de claves y del número de particiones.
<table>
<th>Tamaño de claves RSA
</th>
<th>Claves privadas</th>
<th>Pares de claves</th>
<tr><td>RSA-2048</td>
<td>12.000</td>
<td>9.500</td></tr>
<tr><td>RSA-4096</td>
<td>6.500</td>
<td>5.200</td></tr>
<tr><td>RSA-8192</td>
<td>3.300</td>
<td>2.700</td></tr>

<th>Tamaño de claves ECDSA
</th>
<th>Claves privadas</th>
<th>Pares de claves</th>
<tr><td>P-256</td>
<td>63.000</td>
<td>37.500</td></tr>
<tr><td>P-384</td>
<td>58.000</td>
<td>33.000</td></tr>
<tr><td>P-521</td>
<td>48.000</td>
<td>27.000</td></tr>
<tr><td>BrainpoolP512r1</td>
<td>48.000</td>
<td>27.000</td></tr>

<th>Tamaño de claves simétricas
</th>
<th colspan="2">Claves</th>

<tr><td>AES128</td>
<td colspan="2">126.000</td>
</tr>
<tr><td>AES256</td>
<td colspan="2">112.000</td>
</tr>
<tr><td>DES</td>
<td colspan="2">140.000</td>

</tr>
<tr><td>3DES</td>
<td colspan="2">123.000</td>
</tr>
</table>

## ¿Puedo configurar alta disponibilidad para mi solución {{site.data.keyword.cloud_notm}} HSM?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Sí; para configurar alta disponibilidad entre las particiones de {{site.data.keyword.cloud_notm}} HSM mediante el uso de secretos, consulte la [Guía de instalación de SafeNet Luna Network HSM 7.2![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. Es necesario iniciar una sesión en el portar de soporte de Gemalto.

## ¿Cómo puedo hacer una copia de seguridad de mi configuración de {{site.data.keyword.cloud_notm}} HSM?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
Para hacer una copia de seguridad de su configuración de {{site.data.keyword.cloud_notm}} HSM, consulte el capítulo 6 de la [Guía de administración de dispositivos ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (página 66).
