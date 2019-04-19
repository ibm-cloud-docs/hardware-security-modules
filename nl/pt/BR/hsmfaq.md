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

# Perguntas mais frequentes: IBM Cloud HSM
{: #faqs-ibm-cloud-hsm}

A oferta {{site.data.keyword.cloud}} HSM fornece criptografia dedicada de locatário único, gerenciamento de chave e armazenamento "como um serviço" usando Hardware Security Modules (HSMs).
{:shortdesc}

## O que é um Hardware Security Module (HSM)?
{: #what-is-a-hardware-security-module-hsm}
{: faq}
Um HSM é uma parte do hardware que processa operações criptográficas e não permite que as chaves de criptografia saiam do ambiente criptográfico seguro. Os dados compartilhados, armazenados ou em movimento são criptografados em seu ponto de criação e as empresas podem executar e manter suas próprias políticas de proteção de dados na nuvem.

## De qual HSM o {{site.data.keyword.cloud_notm}} depende?
{: #what-hsm-does-ibm-cloud-rely-on}
{: faq}
O {{site.data.keyword.IBM_notm}} alavanca a tecnologia do Gemalto SafeNet Luna Network HSM para as ofertas Cloud HSM 6.0 e 7.0. Essa solução fornece aos clientes facilidade de acesso a 60 data centers do {{site.data.keyword.cloud_notm}} em todo o mundo, que podem ser usados para resolver seus desafios de conformidade e soberania de dados.

## Qual versão do {{site.data.keyword.cloud_notm}} HSM devo pedir?
{: #which-version-of-ibm-cloud-hsm-should-i-order}
{: faq}
Na maioria dos casos, sempre é necessário pedir a versão mais recente de um HSM. Alguns usuários com versões mais antigas poderão ter problemas de compatibilidade com a alta disponibilidade se eles tiverem HSMs mais antigos existentes. Se você já tiver versões mais antigas, entre em contato com o Suporte para determinar qual versão é a correta para você.

## Posso migrar meu HSM existente para uma nova versão?
{: #can-i-migrate-my-existing-hsm-to-a-new-version}
{: faq}
Seu HSM não pode ser migrado. Em vez disso, cancele seu HSM existente no menu **Dispositivos** e peça uma nova versão.

## O {{site.data.keyword.cloud_notm}} HSM é certificado pelo FIPS?
{: #is-ibm-cloud-hsm-fips-certified}
{: faq}
Sim, o {{site.data.keyword.cloud_notm}} HSM 7.0 é certificado pelo FIPS 140-2 Nível 3 e é designado para garantir que as empresas recebam uma solução confiável e segura para o gerenciamento de seus ativos criptográficos. O IBM Cloud HSM 6.0 é certificado pelo FIPS 140-2 Nível 2 para a infraestrutura de chave pública (PKI), as assinaturas digitais e o armazenamento de chave criptográfica.

## Quais casos posso abordar com o {{site.data.keyword.cloud_notm}} HSM?
{: #what-use-cases-can-I-address-with-ibm-cloud-hsm}
{: faq}
É possível usar o serviço HSM para suportar uma variedade de casos de uso e aplicativos, tais como infraestrutura de chave pública (PKI), assinatura de código, criptografia de banco de dados, assinatura de documentos, capacidade de gerenciamento de direitos digitais (DRM), autenticação, autorização e processamento de transações.

## Quantas partições meu {{site.data.keyword.cloud_notm}} HSM suporta?
{: #how-many-partitions-will-my-ibm-cloud-hsm-support}
{: faq}
O {{site.data.keyword.cloud_notm}} HSM 6.0 e 7.0 suportam até 10 partições.

## Quantas chaves podem ser armazenadas com o {{site.data.keyword.cloud_notm}} HSM 7.0?
{: #how-many-keys-can-be-stored-with-ibm-cloud-hsm-7.0}
{: faq}
A capacidade de chave é calculada criando uma partição e criando chaves até que a partição esteja cheia.
Todos os números são aproximados. A capacidade varia, dependendo dos atributos-chave específicos configurados no modelo de geração de chave e no número de partições.
<table>
<th>Tamanho da chave RSA
</th>
<th>Chaves privadas</th>
<th>Pares de Chaves</th>
<tr><td>RSA-2048</td>
<td>12.000</td>
<td>9.500</td></tr>
<tr><td>RSA-4096</td>
<td>6.500</td>
<td>5.200</td></tr>
<tr><td>RSA-8192</td>
<td>3.300</td>
<td>2.700</td></tr>

<th>Tamanho da chave ECDSA
</th>
<th>Chaves privadas</th>
<th>Pares de Chaves</th>
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

<th>Tamanho da chave simétrica
</th>
<th colspan="2">Keys</th>

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

## Posso configurar a alta disponibilidade para meu {{site.data.keyword.cloud_notm}} HSM?
{: #can-i-configure-high-availability-with-my-ibm-cloud-hsm}
{: faq}
Sim, para configurar a alta disponibilidade entre partições do {{site.data.keyword.cloud_notm}} HSM usando segredos, consulte o [Guia de instalação do SafeNet Luna Network HSM 7.2 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://supportportal.gemalto.com/csm?id=kb_article_view&sys_kb_id=19a81c8bdb9a1fc8d298728dae96197d&sysparm_article=KB0017573){: new_window}. É necessário efetuar login no Portal de suporte do Gemalto.

## Como fazer backup da configuração do meu {{site.data.keyword.cloud_notm}} HSM?
{: #how-can-i-back-up-my-ibm-cloud-hsm-configuration}
{: faq}
Para fazer backup da configuração do seu {{site.data.keyword.cloud_notm}} HSM, consulte o capítulo seis do [Guia de Administração do dispositivo ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/Appliance_Administration_Guide_72.pdf){: new_window} (página 66).
