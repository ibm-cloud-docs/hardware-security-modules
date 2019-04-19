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

# Häufig gestellte Fragen: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

Mit dem Angebot {{site.data.keyword.cloud}} HSM "as a Service" stehen dedizierte, für einzelne Tenants konzipierte Verschlüsselungs-, Schlüsselmanagement- und Speicherfunktionen über Hardwaresicherheitsmodule (HSMs) zur Verfügung.
{:shortdesc}

## Was ist ein Hardwaresicherheitsmodul (Hardware Security Module, HSM)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
Bei einem HSM handelt es sich um eine Hardwarekomponente, die Verschlüsselungsoperationen durchführt und verhindert, dass Verschlüsselungsschlüssel die geschützte Verschlüsselungsumgebung verlassen. Gemeinsam genutzte, gespeichert oder bewegte Daten werden an der Position ihrer Erstellung verschlüsselt; Unternehmen können eigene Datenschutzrichtlinen in der Cloud ausführen und verwalten.

## Welches HSM nutzt {{site.data.keyword.cloud_notm}}?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} nutzt die Gemalto SafeNet Luna Network HSM-Technology für Cloud HSM 6.0- und 7.0-Angebote. Diese Lösung bietet Kunden einfachen Zugriff auf weltweit 60 {{site.data.keyword.cloud_notm}} Rechenzentren, die sie nutzen können, um den Anforderungen im Bereich der Compliance und der Datensouveränität zu begegnen.

## Welche Version von {{site.data.keyword.cloud_notm}} HSM soll ich bestellen?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
In den meisten Fällen sollte grundsätzlich die neueste HSM-Version bestellt werden. Sind bereits ältere HSMs vorhanden, treten bei einigen Benutzern älterer Versionen möglicherweise Kompatibilitätsprobleme im Zusammenhang mit der Hochverfügbarkeit auf. Sind bereits ältere Versionen vorhanden, wenden Sie sich an das Support-Team, um die geeignete Version zu bestimmen.

## Kann ein vorhandenes HSM auf eine neue Version migriert werden?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
Eine Migration des HSMs ist nicht möglich. Entfernen Sie stattdessen das vorhandene HSM aus dem Menü **Geräte** und bestellen Sie eine neue Version.

## Ist {{site.data.keyword.cloud_notm}} HSM den FIPS-Richtlinien entsprechend zertifiziert?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
Ja, {{site.data.keyword.cloud_notm}} HSM 7.0 ist den FIPS 140-2 Level 3-Richtlinien entsprechend zertifiziert und so konzipiert, dass sichergestellt wird, dass Unternehmen eine zuverlässige und sichere Lösung zur Verwaltung ihrer Verschlüsselungsassets erhalten. IBM Cloud HSM 6.0 ist den Richtlinien von FIPS 140-2 Level 2 entsprechend für PKI (Public Key Infrastructure), digitale Signaturen und Verschlüsselungsschlüsselspeicher zertifiziert.

## Für welche Anwendungsfälle kann {{site.data.keyword.cloud_notm}} HSM verwendet werden?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
Der HSM-Service kann zur Unterstützung einer Vielzahl verschiedener Anwendungsfälle und Anwendungen eingesetzt werden. Hierzu gehören z. B. Public Key Infrastructure (PKI), Codesignatur, Datenbankverschlüsselung, Dokumentsignatur, Digital Rights Management (DRM), Authentifizierung und Berechtigung sowie Transaktionsverarbeitung.

## Wie viele Partitionen unterstützt meine Instanz von {{site.data.keyword.cloud_notm}} HSM?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 und 7.0 unterstützen bis zu 10 Partitionen.

## Wie viele Schlüssel können mit {{site.data.keyword.cloud_notm}} HSM 7.0 gespeichert werden?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
Die Schlüsselkapazität wird berechnet, indem eine Partition erstellt und so viele Schlüssel erstellt werden, bis die Partition voll ist.
Alle Zahlen sind näherungsweise berechnet. Die Kapazität variiert in Abhängigkeit von den jeweiligen Schlüsselattributen, die in der Vorlage für die Schlüsselerstellung festgelegt sind, sowie von der Anzahl der Partitionen.
<table>
<th>RSA-Schlüsselgröße
</th>
<th>Private Schlüssel</th>
<th>Schlüsselpaare</th>
<tr><td>RSA-2048</td>
<td>12.000</td>
<td>9.500</td></tr>
<tr><td>RSA-4096</td>
<td>6.500</td>
<td>5.200</td></tr>
<tr><td>RSA-8192</td>
<td>3.300</td>
<td>2.700</td></tr>

<th>ECDSA-Schlüsselgröße
</th>
<th>Private Schlüssel</th>
<th>Schlüsselpaare</th>
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

<th>Größe symmetrischer Schlüssel
</th>
<th colspan="2">Schlüssel</th>

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

## Kann ich Hochverfügbarkeit für meine Instanz von {{site.data.keyword.cloud_notm}} HSM konfigurieren?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Ja. Informationen zur Konfiguration von Hochverfügbarkeit in Partitionen des {{site.data.keyword.cloud_notm}} HSM mithilfe von geheimen Schlüsseln finden Sie in der Dokumentation [SafeNet Luna Network HSM 7.2 Installation Guide ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. Melden Sie sich beim Support-Portal von Gemalto an, falls dies erforderlich sein sollte.

## Wie kann ich meine {{site.data.keyword.cloud_notm}} HSM-Konfiguration sichern?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
Informationen zum Sichern Ihrer {{site.data.keyword.cloud_notm}} HSM-Konfiguration finden Sie in Kapitel 6 der Dokumentation [Appliance Administration Guide ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (Seite 66).
