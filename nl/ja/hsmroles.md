---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM の役割
{: #ibm-cloud-hsm-roles}

このトピックでは、{{site.data.keyword.cloud}} HSM と、ホスト内部にあるかホストに接続された暗号化エンジンにアクセスする役割について説明します。  
{:shortdesc}

## 必須の役割
<li>HSM セキュリティー担当者 (SO): HSM の初期化、(HSM の機能に基づく) HSM ポリシーの設定と変更、アプリケーション・パーティションの作成と削除を担当します。
<li>パーティション・セキュリティー担当者 (PO): パーティションでの暗号担当者役割の初期設定、パスワードのリセット、(HSM やパーティションの機能に基づく) パーティション・レベル・ポリシーの設定と変更を担当します。
<li>暗号担当者 (CO): 暗号ユーザー役割の初期設定と、HSM パーティションでの暗号オブジェクトの作成と変更を担当します。

## オプションの役割
{: #optional-roles}

<li>監査員 (Au): HSM 監査ロギングを担当します。HSM の他の役割から独立しています。
<li>暗号ユーザー (CU): HSM パーティションでの暗号オブジェクトの使用 (暗号化/復号、署名/検証など) を担当します。

## 拡張 Cryptoki モデル
{: #enhanced-cryptoki-model}

SafeNet Luna Network HSM での以下の役割の役割分離は、拡張 Cryptoki モデルに準拠しています。

### HSM セキュリティー担当者 (SO)
{: #hsm-security-officer-so}

HSM SO は、SafeNet Luna Network HSM アプライアンス内の HSM を制御できます。HSM の SO 機能にアクセスするには、最初にアプライアンス管理者としてログインする必要があります。
HSM SO 資格情報を使用して認証されたユーザーは、その他すべてのアプライアンス機能の他に以下の操作を実行できます。
<li>パーティションの作成および削除
<li>HSM のバックアップおよび復元
<li>HSM ポリシーの変更

### パーティション・セキュリティー担当者 (PO)
{: #partition-security-officer-po}

パーティション・セキュリティー担当者は、SafeNet Luna Network HSM 内の 1 つ以上のパーティション (仮想 HSM) を制御できます。パーティション SO の機能にアクセスするには、登録済みクライアント・コンピューターで LunaCM ユーティリティーを使用してログインする必要があります。
パーティションにログインしたパーティション SO は、次の操作を実行できます。
<li>パーティション・ポリシーの変更
<li>パーティションの内容のバックアップおよび復元
<li>暗号担当者役割の初期設定

### 暗号担当者 (CO)
{: #crypto-officer-co}

暗号担当者は、登録済みクライアント・コンピューターで LunaCM ユーティリティーを使用してパーティションへの完全な読み取り/書き込みアクセスが可能です。暗号担当者のパーティション資格情報により、クライアント・アプリケーションは次のような暗号操作を実行できます。
<li>鍵の生成/削除
<li>ラップ/アンラップ
<li>暗号化/復号
<li>署名/検証</li>
また暗号担当者は、オプションの暗号ユーザー役割を初期設定できます。

### 暗号ユーザー (CU)
{: #cypto-user-cu}

暗号ユーザーは、制限付き読み取り専用クライアント・ユーザーです。初期設定された認証済み暗号ユーザーは (署名、検証、暗号化、復号のために) パーティションの既存の暗号マテリアルにアクセスできますが、これらのオブジェクトを操作することはできません (生成、削除、ラップ/アンラップは実行できません)。
暗号ユーザー役割はオプションです。この役割を使用するセキュリティー上の必要がない場合、この役割は初期設定しないでおくことができます。これを初期設定しないでおく場合は、すべてのクライアント・アプリケーションが暗号担当者の資格情報を使用してパーティションにアクセスできます。
