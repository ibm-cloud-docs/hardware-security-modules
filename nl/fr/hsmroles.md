---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Rôles IBM Cloud HSM
{: #ibm-cloud-hsm-roles}

Cette rubrique présente les rôles utilisés pour l'accès à {{site.data.keyword.cloud}} HSM ainsi que le moteur cryptographique intégré ou connecté à l'hôte.  
{:shortdesc}

## Rôles obligatoires
<li>Responsable de la sécurité HSM : responsable de l'initialisation du module HSM, de la définition et de la modification des règles HSM (selon les fonctionnalités du module HSM), de la création et de la suppression des partitions d'application
<li>Responsable de la sécurité de la partition : responsable de l'initialisation du rôle Responsable du chiffrement sur la partition, de la réinitialisation des mots de passe, de la définition et de la modification des règles au niveau de la partition (selon les fonctionnalités des modules HSM et de la partition)
<li>Responsable du chiffrement : responsable de l'initialisation du rôle Utilisateur du chiffrement ainsi que de la création et de la modification des objets cryptographiques dans la partition HSM

## Rôles facultatifs
{: #optional-roles}

<li>Auditeur : responsable de la gestion de la journalisation d'audit HSM, indépendant des autres rôles du module HSM
<li>Utilisateur du chiffrement : responsable de l'utilisation d'objets cryptographiques (chiffrement/déchiffrement, signature/vérification, etc.) dans la partition HSM

## Amélioration du modèle Cryptoki
{: #enhanced-cryptoki-model}

La séparation des rôles dans le module HSM réseau SafeNet Luna suit un modèle Cryptoki amélioré pour les rôles suivants :

### Responsable de la sécurité HSM
{: #hsm-security-officer-so}

Le responsable de la sécurité HSM a le contrôle du module HSM réseau SafeNet Luna. Pour accéder aux fonctions de ce responsable, vous devez tout d'abord vous connecter en tant qu'administrateur du dispositif.
Outre les fonctions du dispositif, un utilisateur authentifié via les données d'authentification du responsable de la sécurité HSM peut :
<li>créer et supprimer des partitions
<li>sauvegarder et restaurer le module HSM
<li>changer les règles HSM

### Responsable de la sécurité de la partition 
{: #partition-security-officer-po}

Le responsable de la sécurité de la partition a le contrôle d'une ou de plusieurs partitions (modules HSM virtuels) dans le module HSM réseau SafeNet Luna. Pour accéder à ses fonctions, vous devez vous connecter via l'utilitaire LunaCM sur un ordinateur client enregistré.
De plus, il peut lorsqu'il est connecté à la partition :
<li>modifier des règles de partition
<li>sauvegarder et restaurer le contenu de la partition
<li>initialiser le rôle Responsable du chiffrement

### Responsable du chiffrement 
{: #crypto-officer-co}

Le responsable du chiffrement a un accès en lecture/écriture à la partition via l'utilitaire LunaCM sur un ordinateur client enregistré. Ses données d'identification de partition permettent à une application client d'effectuer des opérations de chiffrement, notamment les suivantes :
<li>Génération/suppression de clé
<li>Encapsulation/désencapsulation
<li>Chiffrement/déchiffrement
<li>Signature/vérification</li>
Le responsable du chiffrement peut également initialiser le rôle facultatif Utilisateur du chiffrement.

### Utilisateur du chiffrement 
{: #cypto-user-cu}

L'utilisateur du chiffrement est un utilisateur client en lecture seule restreint. Après l'initialisation, cet utilisateur authentifié peut accéder aux matériels cryptographiques existants sur la partition pour signer, vérifier, chiffrer et déchiffrer. Cependant, il ne peut pas manipuler ces objets (génération, suppression, encapsulage et désencapsulage).
Ce rôle est facultatif. Si vous avez des exigences de sécurité pour ce rôle, il peut ne pas être initialisé et toutes les applications client peuvent accéder à la partition en utilisant les données d'identification du responsable du chiffrement.
