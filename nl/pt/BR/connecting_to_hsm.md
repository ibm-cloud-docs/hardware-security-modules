---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Conectando-se ao IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

As etapas a seguir descrevem como conectar a VPN do Hardware Security Module (HSM) à sua conta do cliente. Também é possível se conectar por meio de um servidor em sua conta que tenha conectividade com a VLAN privada na qual o HSM foi provisionado.
{:shortdesc}

![Arquitetura de uma rede com o HSM](/images/Connecting_to_HSM-01.png "Arquitetura do HSM")

1. Efetue login no seu HSM usando o ID do usuário e a senha fornecidos em *Detalhes do dispositivo* por meio de sua VPN ou em um servidor localizado na mesma VLAN privada.
` #ssh customer_admin@10.1.1.101 `

2. Mude a senha `customer_admin` do HSM:
`#user password`

3. Ativar autenticação baseada em infraestrutura de chave pública (PKI):
```
#ssh-keygen -b 2048 -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
A impressão digital da chave é: 6e: 7a: 73:e1:2a: 54:8f: 99:3e: 6a: 56 :f8:38:22 :fb:a6 root@host
```
Dois arquivos são criados. O primeiro é um arquivo de chave privada que permanece no host de conexão e o outro é um arquivo de chave pública que é enviado ao dispositivo do HSM.

4. Use o Secure Copy Protocol (SCP) para enviar a pública para o dispositivo '# scp /root/.ssh/id_rsa/pub'.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. No dispositivo, verifique as configurações padrão do serviço de autenticação de chave pública.
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. Verifique se não há entradas de chave pública por padrão.
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. Inclua a chave pública que foi enviada no dispositivo.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. Verifique a lista de chaves públicas.
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. Verifique se a impressão digital relatada corresponde à impressão digital gerada originalmente no host de conexão.
