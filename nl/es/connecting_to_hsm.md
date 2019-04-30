---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Conexión a IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

En los pasos siguientes se describe cómo conectar la VPN de HSM (Hardware Security Module) a su cuenta de cliente. También puede conectarse desde un servidor de la cuenta que tenga conectividad a la VLAN privada en la que se ha suministrado el HSM.
{:shortdesc}

![Arquitectura de una red con el HSM](/images/Connecting_to_HSM-01.png "Arquitectura de HSM")

1. Inicie sesión en el HSM utilizando el ID de usuario y la contraseña proporcionados en *Detalles de dispositivo* mediante su VPN o a un servidor ubicado en la misma VLAN privada.
`#ssh customer_admin@10.1.1.101`

2. Cambie la contraseña `customer_admin` de HSM:
`#user password`

3. Habilite la autenticación basada en la infraestructura de clave pública (PKI):
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
Se crean dos archivos. El primero es un archivo de clave pública, que permanece en el host en conexión, y el otro es un archivo de clave pública que se envía al dispositivo de HSM.

4. Utilice Secure Copy Protocol (SCP) para enviar la clave pública al dispositivo '# scp /root/.ssh/id_rsa/pub'.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. En el dispositivo, verifique los valores predeterminados del servicio de Autenticación de clave pública.
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. Verifique que no haya entradas de clave pública de forma predeterminada.
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. Añada la clave pública enviada al dispositivo.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. Verifique la lista de claves públicas.
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. Compruebe que la huella dactilar notificada coincide con la huella dactilar generada originalmente en el host en conexión.
