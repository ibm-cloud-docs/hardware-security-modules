---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# 連接至 IBM Cloud HSM
{: #connecting-to-ibm-cloud-hsm}

下列步驟概述如何將 Hardware Security Module (HSM) VPN 連接至您的客戶帳號。您也可以從帳戶上具有連線功能的伺服器，連接至其中已佈建 HSM 的專用 VLAN。
{:shortdesc}

![含有 HSM 的網路架構](/images/Connecting_to_HSM-01.png "HSM 架構")

1. 使用*裝置詳細資料* 上提供的使用者 ID 和密碼透過 VPN 登入 HSM，或登入位於相同專用 VLAN 的伺服器。`#ssh customer_admin@10.1.1.101`

2. 變更 HSM `customer_admin` 密碼：
`#user password`

3. 啟用公開金鑰基礎架構 (PKI) 型鑑別：
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
建立了兩個檔案。第一個是私密金鑰檔，它會留在連接主機上，還有一個就是傳送至 HSM 應用裝置的公開金鑰檔。

4. 使用 Secure Copy Protocol (SCP) 將公開金鑰傳送至應用裝置 '# scp /root/.ssh/id_rsa/pub'。
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. 在此應用裝置上，驗證「公開金鑰鑑別」服務的預設值。
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```

6. 驗證預設情況下沒有任何公開金鑰項目。
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
Command Result : 0 (Success)
```
7. 新增已傳送至應用裝置的公開金鑰。
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. 驗證公開金鑰清單。
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. 確認報告的指紋符合連接主機上原始產生的指紋。
