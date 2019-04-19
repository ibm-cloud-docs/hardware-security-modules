---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connessione a IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

La seguente procedura descrive come connettere la VPN HSM (Hardware Security Module) al tuo account cliente. Puoi collegarti anche da un server nel tuo account che dispone di connettività alla VLAN privata in cui è stato eseguito il provisioning dell'HSM.
{:shortdesc}

![Architettura della rete con l'HSM](/images/Connecting_to_HSM-01.png "Architettura HSM")

1. Accedi al tuo HSM utilizzando l'ID utente e la password forniti in *Device Details* tramite la tua VPN o a un server ubicato nella stessa VLAN privata.
`#ssh customer_admin@10.1.1.101`

2. Modifica la password HSM `customer_admin`:
`#user password`

3. Abilita l'autenticazione basata sulla PKI (Public Key Infrastructure):
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
Vengono creati due file. Il primo è un file della chiave privata, che si trova sull'host di connessione e un file della chiave pubblica che viene inviato all'applicazione HSM.

4. Utilizza il SCP (Secure Copy Protocol) per inviare il file della chiave pubblica all'applicazione '# scp /root/.ssh/id_rsa/pub'.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. Nell'applicazione, verifica le impostazioni predefinite del servizio di autenticazione della chiave pubblica.
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. Verifica che non ci siano voci della chiave pubblica predefinite.
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. Aggiungi la chiave pubblica che è stata inviata all'applicazione.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. Verifica l'elenco delle chiavi pubbliche.
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. Controlla che l'impronta digitale selezionata corrisponda a quella generata in origine nell'host di connessione.
