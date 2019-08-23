---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Funções do IBM Cloud HSM
{: #ibm-cloud-hsm-roles}

Este tópico descreve as funções que acessam o {{site.data.keyword.cloud}} HSM e o mecanismo criptográfico dentro ou conectado ao host.  
{:shortdesc}

## Funções obrigatórias
<li>HSM Security Officer (SO): responsável pela inicialização do HSM, pela configuração e mudança das Políticas do HSM (com base nos recursos do HSM), pela criação e exclusão de partições de aplicativos
<li>Partition Security Officer (PO): responsável pela inicialização da função Crypto Officer na partição, pela reconfiguração de senhas, pela configuração e mudança das Políticas do nível de partição (com base nos recursos do HSM e da partição)
<li>Crypto Officer (CO): responsável pela inicialização da função Crypto User e pela criação e modificação dos objetos criptográficos na partição do HSM

## Funções opcionais
{: #optional-roles}

<li>Auditor (Au): responsável pelo gerenciamento da criação de log de auditoria do HSM, independente de outras funções no HSM
<li>Crypto User (CU): responsável pelo uso de objetos criptográficos (criptografar/decriptografar, assinar/verificar e mais) na partição do HSM

## Modelo Cryptoki aprimorado
{: #enhanced-cryptoki-model}

A separação de funções no SafeNet Luna Network HSM segue um modelo Cryptoki aprimorado para as funções a seguir:

### HSM Security Officer (SO)
{: #hsm-security-officer-so}

O SO do HSM tem o controle do HSM dentro do dispositivo SafeNet Luna Network HSM. Para acessar as funções de SO do HSM, deve-se primeiro estar com login efetuado como administrador do dispositivo.
Além de todas as outras funções do dispositivo, um usuário autenticado com a credencial do SO do HSM pode:
<li>Criar e excluir partições
<li>Fazer backup e restaurar o HSM
<li>Mudar as políticas do HSM

### Partition Security Officer (PO)
{: #partition-security-officer-po}

O Responsável pela segurança da partição tem controle de uma ou mais partições (HSMs virtuais) dentro do SafeNet Luna Network HSM. Para acessar as funções do SO da partição, deve-se efetuar login usando o utilitário LunaCM em um computador cliente registrado.
O S.O. da partição, quando está com login efetuado na partição, pode:
<li>Modificar as políticas da partição
<li>Fazer backup e restaurar o conteúdo da partição
<li>Inicializar a função Crypto Officer

### Agente Crypto (CO)
{: #crypto-officer-co}

O Crypto Officer tem acesso de leitura/gravação total à partição por meio do utilitário LunaCM em um computador cliente registrado. A credencial de partição do Crypto Officer permite que um aplicativo Cliente execute qualquer operação criptográfica, incluindo:
<li>Geração/exclusão de chave
<li>Agrupar/desagrupar
<li>Criptografar/decriptografar
<li>Assinar/verificar</li>
O Crypto Officer também pode inicializar a função opcional Crypto User.

### Usuário Crypto (CU)
{: #cypto-user-cu}

O Crypto User é um usuário cliente restrito com autorização somente leitura. Após a inicialização, o Crypto User autenticado pode acessar materiais criptográficos já existentes na partição (para assinar, verificar, criptografar, decriptografar), mas não pode manipular esses objetos (gerar, excluir ou agrupar/desagrupar).
A função Crypto User é opcional. Se você não tiver nenhum requisito de segurança para essa função, ela poderá permanecer não inicializada, e todos os aplicativos Clientes poderão acessar a partição usando a credencial do Crypto Officer.
