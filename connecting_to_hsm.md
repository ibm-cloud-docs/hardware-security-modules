---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Connecting to IBM Cloud HSM

The following steps outline how to connect the Hardware Security Module (HSM) VPN to your customer account. You can also connect from a server on your account that has connectivity to the private VLAN on which the HSM has been provisioned.
{:shortdesc}

![Architecture of a network with the HSM](/images/Connecting_to_HSM-01.png "HSM Architecture")

1. Log in to your HSM using the user id and password provided on *Device Details* through your VPN or to a server located on the same private VLAN.
`#ssh customer_admin@10.1.1.101`

2. Change the HSM `customer_admin` password:
`#user password`

3. Enable public key infrastructure (PKI)-based authentication:
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
Two files are created. The first is a private key file, which stays on the connecting host, and a public key file that is sent to the HSM appliance.

4. Use Secure Copy Protocol (SCP) to send the public to the appliance '# scp /root/.ssh/id_rsa/pub'.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. On the appliance, verify the default settings of the Public Key Authentication service.
```[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)```

6. Verify that there are no public key entries by default.
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. Add the public key that was sent to the appliance.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. Verify the list of public keys.
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. Check that the fingerprint reported matches the fingerprint originally generated on the connecting host.
