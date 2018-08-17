---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Création de partitions IBM Cloud HSM

Dans un module {{site.data.keyword.cloud}} HSM (Hardware Security Module), des espaces de travail cryptographiques distincts doivent être initialisés et désignés pour les clients. Un espace de travail, ou *partition*, et tout son contenu est protégé par un chiffrement dérivé de son authentification. Seul un client qui présente l'identification correcte est autorisé à voir la partition et à travailler sur son contenu.
{:shortdesc}

Lors de la création de partitions, rappelez-vous que les noms de partition, également dénommés labels, doivent être unique dans le module HSM. Vous ne pouvez pas créer sur un module HSM deux partitions avec le même label. Le nom que vous attribuez à votre partition est le label que voient les applications PKCS (Public-Key Cryptographic Standards ) #11.

1. Connectez-vous en tant qu'administrateur HSM avec le mot de passe utilisé pour l'initialisation de ce module.
```
[myLuna] lusash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. Créez la partition.
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
