---

copyright:
  years: 2017,2018
lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# ハードウェア・ファイアウォール (専用) の構成
{: #configuring-the-hardware-firewall-dedicated-}

ファイアウォールを初めて VLAN に追加したとき、最初は、ファイアウォールを通じてすべてのトラフィックを許可する一連のルールが配備されます。 ファイアウォールの構成手順は、特定のインターネット・アドレスから特定の IP アドレス/ポートへのアクセスを許容し、その他のソースからのトラフィックを拒否するための一連のルールを作成するだけの非常に単純なものです。

## ルールの編集

ファイアウォール・ルールを編集するには、次の手順を行います。

1. ブラウザーから、[カスタマー・ポータル![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){: new_window}を開き、アカウントにログインします。
2. カスタマー・ポータル・ナビゲーションで**「ネットワーク」>「IP 管理」>「VLAN」**を選択します。 インフラストラクチャー内の VLAN が 1 行に 1 つずつ示されています。  管理する VLAN に関連付けられている Firewall-vlanXXXX.networklayer.com リンクをクリックして、**「デバイスの詳細」**ページに移動します。 ルールが存在する場合、「状況」に、そのファイアウォールが「すべてのルールを処理」していると示されていることを確認します。万一、実装したルールがユーザー環境に予期せぬ影響を与えている場合は、この領域の「ルールのバイパス」をクリックすることで、ルールをバイパスすることを選択できます。
3. ルールの更新を開始するため、**「ルール」**タブをクリックします。 このページには、IPv4 アドレスおよび IPv6 アドレスで有効な現行ルールを示す各セクションが表示されます。  ルールが 1 つも実装されていないと、フェード状態のプレースホルダーが表示されます。  対応する行をクリックして、個々のルールを編集します。  このルール・リストは「作業構成」と呼ばれます。 「作業構成」は、作成プロセス中で、まだファイアウォールに適用されていない一連のルールです。 ルールを編集、追加、削除して、ルール・セットを整えます。  ルールは処理される順序で表示され、小さいほうの番号のルールが、大きいほうの番号のルールよりも優先されます (ルール 1 がパケットの通過を許可すれば、ルール 2 以降はそのパケットに適用されません)。
4. ルールをクリックして編集するか、テーブルの最下部にある正符号をクリックしてルールを追加します。 マイナス・アイコンをクリックすると、そのルールが削除されます。 ルールは、入力すると同時に自動的に検証されます。

    フィールドは以下のとおりです。

    **アクション:** このルールに一致したトラフィックを「permit (許可)」または「deny (拒否)」します。

    **ソース:**「any (すべて)」に設定するか、特定の IP アドレスを設定するか、または特定のサブネットのネットワーク・アドレスを設定できます。

    **CIDR:** 選択したソースの標準 CIDR 表記を示します。  「32」を指定すると、単一の IP に対してルールが実装されます。一方、例えば「24」を指定すると、256 個の IP に対してルールが実装されます。

    **宛先:**「any (すべて)」に設定するか、特定の IP アドレスを設定するか、または特定のサブネットのネットワーク・アドレスを設定できます。

    **CIDR:** 選択した宛先の標準 CIDR 表記を示します。

    **ポートの範囲:** これら 2 つのフィールドは、ルールの適用対象となるポートの範囲 (1 から 65535) を示します。

    **プロトコル:** ルールの適用対象となるプロトコルを選択します (TCP/GRE/ICMP/UDP/PPTP/AH/ESP)。

    **メモ:** このルールに関する任意のメモを入力するためのフィールドです。
    
5. 「作業構成」が完了したら、「**ルールの更新**」ボタンを押して「作業構成」をファイアウォールに適用します。 2 分以内にルールが有効になります。

## 共通ポート

| プロトコル | ポート |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| リモート・デスクトップ | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC クライアント | 5900 |
| Urchin | 9999 または 10000 ||
