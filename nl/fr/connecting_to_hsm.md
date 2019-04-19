---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connexion au module IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

La procédure suivante décrit comment connecter le réseau VPN du module de sécurité matérielle (HSM) à votre compte client. Vous pouvez également vous connecter depuis un serveur sur votre compte disposant d'une connectivité au VLAN privé sur lequel le module a été implanté.
{:shortdesc}

![Architecture d'un réseau avec le module HSM](/images/Connecting_to_HSM-01.png "Architecture du module HSM")

1. Connectez-vous à votre module HSM avec l'ID et le mot de passe indiqués sur *Device Details* via votre réseau privé ou à un serveur situé sur le même VLAN privé.
`#ssh customer_admin@10.1.1.101`

2. Changez le mot de passe `customer_admin` du module HSM :
`#user password`

3. Activez l'authentification passée sur l'infrastructure à clés publiques (PKI) :
```
#ssh-keygen -b 2048 -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6 root@host
```
Deux fichiers sont créés. Le premier est un fichier de clé privée qui demeure sur l'hôte qui se connecte, et le second, un fichier de clé publique qui est envoyé au dispositif HSM.

4. Utilisez le protocole SCP (Secure Copy Protocol) pour envoyer la clé publique au dispositif '# scp /root/.ssh/id_rsa/pub'.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. Sur le dispositif, vérifiez les paramètres par défaut du service d'authentification par clé publique.
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. Vérifiez qu'il n'existe aucune entrée de clé publique par défaut.
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. Ajoutez la clé publique envoyée au dispositif.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. Vérifiez la liste des clés publiques.
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. Vérifiez que l'empreinte signalée correspond à celle générée à l'origine sur l'hôte qui se connecte.
