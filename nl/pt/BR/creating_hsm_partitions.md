---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Criando partições do IBM Cloud HSM

Dentro de um {{site.data.keyword.cloud}} Hardware Security Module (HSM), espaços de trabalho criptográficos separados devem ser inicializados e designados para os clientes. Um espaço de trabalho ou uma *partição* e todos os seus conteúdos são protegidos por criptografia derivada de sua autenticação. Somente um cliente que apresente a autenticação apropriada terá a permissão para ver a partição e trabalhar com seu conteúdo.
{:shortdesc}

Ao criar suas partições, esteja ciente de que os nomes das partições, também conhecidos como rótulos, devem ser exclusivos no HSM. Não é possível criar duas partições com o mesmo rótulo em um HSM. O nome que você dá à sua partição é o rótulo que é visto pelos aplicativos Padrões de Criptografia de Chave Pública (PKCS) nº 11.

1. Efetue login como o Administrador do HSM com a senha usada para inicializar o HSM.
```
[myLuna] lusash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Resultado do Comando: 0 (Sucesso)
```
2. Crie a partição.
```
[myLuna] Lunash:>partition create - partition customerPartionProd
Please ensure that you have purchased licenses for at least this number of partitions: 1
If you are sure to continue then type proceed, otherwise type quit.
> proceed
Processing...
Please enter a password for the partition
>**************
Please re-enter password to confirm:
>**************
Please enter the cloning domain to use when creating this partition (press enter to use the default domain):
> MyDomain
partition create successful
Command Result : 0 (Success)
```
