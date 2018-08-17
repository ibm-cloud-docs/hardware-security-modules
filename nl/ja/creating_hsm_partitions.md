---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM パーティションの作成

{{site.data.keyword.cloud}} Hardware Security Module (HSM) 内で、各クライアント用に別個の暗号化ワークスペースを初期化して指定する必要があります。ワークスペース (つまり*パーティション*) と、そのすべてのコンテンツは、その認証によって有効になる暗号化によって保護されます。適切な認証を行ったクライアントだけにパーティションが表示され、そのコンテンツを扱うことが許可されます。
{:shortdesc}

パーティションを作成するとき、HSM 内で固有のパーティション名 (ラベルとも呼ばれる) を付ける必要があることに注意してください。1 つの HSM 上で、同じラベルを持つ 2 つのパーティションを作成することはできません。パーティションに付ける名前は、Public-Key Cryptographic Standards (PKCS) #11 アプリケーションによって参照されるラベルになります。

1. HSM の初期化に使用したパスワードによって HSM Administrator としてログインします。
```
[myLuna] lusash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. パーティションを作成します。
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
