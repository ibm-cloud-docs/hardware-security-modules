---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM への接続

以下の手順は、お客様のカスタマー・アカウントに属する Hardware Security Module (HSM) VPN に接続する方法の概要を示しています。HSM がプロビジョンされているプライベート VLAN に接続できるアカウントに属するサーバーから接続することもできます。
{:shortdesc}

1. VPN を介して*「デバイスの詳細」*で提供したユーザー ID とパスワードを使用して HSM にログインするか、同じプライベート VLAN 上にあるサーバーにログインします。

`#ssh customer_admin@10.1.1.101`
2. HSM の「customer_admin」パスワードを変更します。
`#user password`
3. 公開鍵インフラストラクチャー (PKI) に基づく認証を有効にします。
```
#ssh-keygen -b 2048 -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Ener same passpharase again:
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6 root@host
```
2 つのファイルが作成されます。最初のものは接続元ホストに保存される秘密鍵ファイルで、もう 1 つは HSM アプライアンスに送信される公開鍵ファイルです。

4. Secure Copy Protocol (SCP) を使用して、公開鍵をアプライアンス「# scp /root/.ssh/id_rsa/pub」に送信します。
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. アプライアンス上で、公開鍵認証サービスのデフォルト設定を確認します。
```
[myLuna] lunash:>sysconf -ssh show
SSH is unrestricted.
Password authentication is enabled
Public key authentication is enabled
Command Result : 0 (Success)
```
6. デフォルトで公開鍵エントリーがないことを確認します。
```
[myLuna]
lunash:>sysconf -ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
--------------------------------------------------------------------
Command Result : 0 (Success)
```
7. アプライアンスに送信された公開鍵を追加します。
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Public key added
Command Result : 0 (Success)
```
8. 公開鍵のリストを確認します。
```
[myLuna] lunash:>sysconf - ssh publickey list
SSH Public Keys for user 'admin':
Name Type Bits Fingerprint
--------------------------------------------------------------------
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Command Result : 0 (Success)
```
9. 報告されたフィンガープリントが接続元ホストで生成された元のフィンガープリントと一致することを確認します。
