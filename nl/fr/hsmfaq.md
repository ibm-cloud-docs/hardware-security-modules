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

# FAQ : IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

L'offre {{site.data.keyword.cloud}} HSM fournit un chiffrement dédié à service exclusif, une gestion des clés, et un stockage "en tant que service" à l'aide de modules HSM (Hardware Security Modules).
{:shortdesc}

## En quoi consiste un module HSM (Hardware Security Module) ?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
Un module HSM est un composant matériel qui traite les opérations de chiffrement et ne permet pas aux clés de chiffrement de sortir de l'environnement de chiffrement sécurisé. Les données, partagées, stockées ou en mouvement, sont chiffrées à leur point de création et les entreprises peuvent exécuter et procéder à la maintenance de leur règles de protection des données dans le cloud.

## Sur quel module HSM {{site.data.keyword.cloud_notm}} s'appuie-t-il ?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
{{site.data.keyword.IBM_notm}} optimise la technologie du module HSM réseau Gemalto SafeNet Luna pour les offres Cloud HSM 6.0 et 7.0. Cette solution permet aux clients d'accéder facilement à 60 centres de données {{site.data.keyword.cloud_notm}} dans le monde qu'ils peuvent utiliser pour résoudre les défis de conformité et de souveraineté des données.

## Quelle version d'{{site.data.keyword.cloud_notm}} HSM dois-je commander ?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
Dans la plupart des cas, vous devez toujours commander la version HSM la plus récente. Certains utilisateurs avec des versions HSM plus anciennes pourraient rencontrer des problèmes de compatibilité. Si vous disposez déjà d'anciennes versions, contactez le support pour déterminer la version adéquate.

## Puis-je migrer mon module HSM vers une nouvelle version ?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
Vous ne pouvez pas migrer votre module HSM. A la place, annulez votre module HSM existant depuis le menu **Devices** et commandez une nouvelle version.

## {{site.data.keyword.cloud_notm}} HSM FIPS dispose-t-il d'une certification ?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
Oui, {{site.data.keyword.cloud_notm}} HSM 7.0 dispose d'une certification FIPS 140-2 Level 3 et est conçu pour garantir que les entreprises disposent d'une solution fiable et sécurisée pour la gestion de leurs actifs cryptographiques. IBM Cloud HSM 6.0 dispose d'une certification FIPS 140-2 Level 2 pour PKI (Public Key Infrastructure), les signatures numériques et le stockage de clé cryptographique.

## Quels cas d'utilisation puis-je gérer avec {{site.data.keyword.cloud_notm}} HSM ?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
Vous pouvez utiliser le service HSM pour traiter une grande variété de cas d'utilisation et d'applications comme PKI (Public Key Infrastructure), la signature du code, le chiffrement de base de données, la signature de document, la gestion des droits numériques (GDN), l'authentification et l'autorisation, et le traitement de transaction.

## Combien de partitions mon module {{site.data.keyword.cloud_notm}} prend-t-il en charge ?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
{{site.data.keyword.cloud_notm}} HSM 6.0 et 7.0 prennent en charge jusqu'à 10 partitions.

## Combien de clés peuvent être stockées avec {{site.data.keyword.cloud_notm}} HSM 7.0 ?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
La capacité de clé est calculée en créant une partition et des clés jusqu'à ce que la partition soit complète.
Tous ces chiffres sont approximatifs. La capacité varie en fonction d'attributs de clé spécifiques définis dans le modèle de génération de clés et du nombre de partitions.
<table>
<th>Taille de clé RSA
</th>
<th>Clés privées</th>
<th>Paires de clés</th>
<tr><td>RSA-2048</td>
<td>12 000</td>
<td>9 500</td></tr>
<tr><td>RSA-4096</td>
<td>6 500</td>
<td>5 200</td></tr>
<tr><td>RSA-8192</td>
<td>3 300</td>
<td>2 700</td></tr>

<th>Taille de clé ECDSA
</th>
<th>Clés privées</th>
<th>Paires de clés</th>
<tr><td>P-256</td>
<td>63 000</td>
<td>37 500</td></tr>
<tr><td>P-384</td>
<td>58 000</td>
<td>33 000</td></tr>
<tr><td>P-521</td>
<td>48 000</td>
<td>27 000</td></tr>
<tr><td>BrainpoolP512r1</td>
<td>48 000</td>
<td>27 000</td></tr>

<th>Taille de clé symétrique
</th>
<th colspan="2">Clés</th>

<tr><td>AES128</td>
<td colspan="2">126 000</td>
</tr>
<tr><td>AES256</td>
<td colspan="2">112 000</td>
</tr>
<tr><td>DES</td>
<td colspan="2">140 000</td>

</tr>
<tr><td>3DES</td>
<td colspan="2">123 000</td>
</tr>
</table>

## Puis-je configurer la haute disponibilité pour mon module {{site.data.keyword.cloud_notm}} HSM ?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Oui, pour configurer la haute disponibilité dans les partitions du module {{site.data.keyword.cloud_notm}} HSM en utilisant des secrets, voir le document [SafeNet Luna Network HSM 7.2 Installation Guide ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. Il est nécessaire de se connecter au portail de support Gemalto.

## Comment puis-je sauvegarder ma configuration {{site.data.keyword.cloud_notm}} HSM ?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
Pour sauvegarder votre configuration {{site.data.keyword.cloud_notm}} HSM, consultez le chapitre 6 du document [Appliance Administration Guide ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (page 66).
