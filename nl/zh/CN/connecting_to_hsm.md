---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# 连接到 IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

以下各步骤概述如何将 Hardware Security Module (HSM) VPN 连接到客户帐户。如果帐户上的服务器已经连接到供应 HSM 的专用 VLAN，那么还可以通过此服务器进行连接。
{:shortdesc}

![使用 HSM 的网络体系结构](/images/Connecting_to_HSM-01.png "HSM 体系结构")

1. 使用*设备详细信息*上提供的用户标识和密码，通过 VPN 登录到 HSM，或登录到位于同一专用 VLAN 上的服务器。`#ssh customer_admin@10.1.1.101`

2. 更改 HSM `customer_admin` 密码：`#user password`

3. 启用基于公用密钥基础架构 (PKI) 的认证：
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
这将创建两个文件。第一个是专用密钥文件，存放在连接主机上；另一个是公用密钥文件，会发送到 HSM 设备。

4. 使用安全复制协议 (SCP) 将公用密钥文件发送至设备“# scp /root/.ssh/id_rsa/pub”。
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. 在设备上，验证“公用密钥认证”服务的缺省设置。
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. 验证是否缺省情况下没有公用密钥条目。
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. 添加已发送到设备的公用密钥。
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. 验证公用密钥列表。
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. 检查所报告的指纹与连接主机上原始生成的指纹是否匹配。
