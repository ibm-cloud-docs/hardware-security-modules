---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, frequently asked questions, FAQs, cryptographic, symmetrical, keys, secrets

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}

# FAQ: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

L'offerta {{site.data.keyword.cloud}} HSM fornisce codifica a singolo tenant, gestione della chiave e archiviazione "as a service" dedicate utilizzando i HSM (Hardware Security Module).
{:shortdesc}

## Cosa è l'HSM (Hardware Security Module)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
Un HSM è una parte di hardware che elabora le operazioni crittografate e non consente alle chiavi di crittografia di lasciare l'ambiente crittografato sicuro. I dati codificati, archiviati o attivi, sono crittografati al momento della creazione e le aziende possono eseguire e conservare le proprie politiche di protezione dei dati nel cloud.

## Su cosa si basa {{site.data.keyword.cloud_notm}}?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} utilizza la tecnologia Gemalto SafeNet Luna Network HSM per le offerte Cloud HSM 6.0 e 7.0. Questa soluzione fornisce ai clienti un facile accesso a 60 data center {{site.data.keyword.cloud_notm}} nel mondo che possono utilizzare per risolvere le proprie difficoltà di sovranità dei dati e di conformità.

## Quale versione di {{site.data.keyword.cloud_notm}} HSM dovrei ordinare?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
In molti casi, dovresti ordinare sempre la versione più recente di un HSM. Alcuni utenti potrebbero avere problemi di compatibilità con l'alta disponibilità se dispongono di HSM esistenti meno recenti. Se già hai delle versioni meno recenti, contatta il supporto per determinare quale versione è quella giusta per te.

## Posso migrare il mio HSM esistente a una nuova versione?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
Il tuo HSM non può essere migrato. Invece, elimina il tuo HSM esistente dal menu **Devices** e ordina una nuova versione.

## {{site.data.keyword.cloud_notm}} HSM è certificato FIPS?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
Sì, {{site.data.keyword.cloud_notm}} HSM 7.0 è certificato FIPS 140-2 Level 3 ed è progettato per garantire che le aziende ricevano una soluzione sicura e affidabile per la gestione dei propri asset crittografati. IBM Cloud HSM 6.0 è certificato FIPS 140-2 Level 2 per la PKI (Public Key Infrastructure), le firme digitali e l'archiviazione della chiave crittografica.

## Quali casi di utilizzo posso risolvere con {{site.data.keyword.cloud_notm}} HSM?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
Puoi utilizzare il servizio HSM per supportare molti casi di utilizzo e applicazioni come la PKI (Public Key Infrastructure), la firma del codice, la codifica del database, la firma del documento, la DRM (Digital Rights Management), l'autenticazione e l'autorizzazione e l'elaborazione della transazione.

## Quante partizioni supporterà il mio {{site.data.keyword.cloud_notm}} HSM?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 e 7.0 supportano fino a 10 partizioni.

## Quante chiavi possono essere archiviate con {{site.data.keyword.cloud_notm}} HSM 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
La capacità di chiavi viene calcolata creando una partizione e creando le chiavi finché non è piena.
Tutti i numeri sono approssimativi. La capacità varia a seconda degli attributi della chiave specifici nel template di generazione della chiave e al numero di partizioni.
<table>
<th>Dimensione chiave RSA
</th>
<th>Chiavi private</th>
<th>Coppie di chiavi</th>
<tr><td>RSA-2048</td>
<td>12.000</td>
<td>9.500</td></tr>
<tr><td>RSA-4096</td>
<td>6.500</td>
<td>5.200</td></tr>
<tr><td>RSA-8192</td>
<td>3.300</td>
<td>2.700</td></tr>

<th>Dimensione chiave ECDSA
</th>
<th>Chiavi private</th>
<th>Coppie di chiavi</th>
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

<th>Dimensione chiave simmetrica
</th>
<th colspan="2">Chiavi</th>

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

## Posso configurare l'alta disponibilità per il mio {{site.data.keyword.cloud_notm}} HSM?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Sì, per configurare l'alta disponibilità tra le partizioni di {{site.data.keyword.cloud_notm}} HSM utilizzando i segreti, vedi [SafeNet Luna Network HSM 7.2 Installation Guide ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. Accedi a Gemalto Support Portal se necessario.

## Come eseguo il backup della mia configurazione di {{site.data.keyword.cloud_notm}} HSM?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
Per eseguire il backup della tua configurazione di {{site.data.keyword.cloud_notm}} HSM, vedi il capitolo 6 di [Appliance Administration Guide ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (pagina 66).
