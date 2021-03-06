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

# パブリック VLAN へのハードウェア・ファイアウォール (専用) の追加
{: #adding-a-hardware-firewall-dedicated-to-a-public-vlan}

ハードウェア・ファイアウォール (専用) は、サーバー注文の一部として注文することはできません。少なくとも 1 つのパブリック計算ノードを確立し、関連付けられた VLAN を追加した後で、注文する必要があります。

VLAN に保護を追加するには、以下の手順で、VLAN ページからハードウェア・ファイアウォール (専用) を注文します。

1. ブラウザーから、[カスタマー・ポータル![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){: new_window}を開き、アカウントにログインします。
2. カスタマー・ポータル・ナビゲーションで**「ネットワーク」>「IP 管理」> 「VLAN」**を選択して、VLAN ページに移動します。 インフラストラクチャー内の VLAN が 1 行に 1 つずつ示されています。 「VLAN 番号」と「プライマリー・ルーター」の情報は、IBM© Cloud によって自動的に取り込まれています。この情報は、実際の VLAN 番号とその VLAN 上に構成されているルーターを示しています。 「名前」フィールドを使用して、識別可能な名称を定義できます。 右端の列「ゲートウェイ/ファイアウォール」には、その VLAN に対して装備されているファイアウォール保護の詳細が記載されています (装備されている場合)。 

	**ヒント:** パブリック VLAN のみが表示されるように VLAN テーブルをフィルタリングするには、**「フィルター」**タブをクリックし、「プライマリー・ルーター」フィールドに「fcr」と入力して、**「フィルター」**ボタンをクリックします。
3. 保護対象の VLAN を見つけて、同じ行の**「ファイアウォールの追加」**リンクをクリックします。 このリンクにより、**「ハードウェア・ファイアウォール (専用) の注文」**ページが開きます。 「ゲートウェイ/ファイアウォール」列にデータが既に取り込まれている場合は、その VLAN に既にファイアウォールまたはネットワーク・ゲートウェイが関連付けられており、先の手順に進むためには、デバイスを削除する必要があります。
4. **「ハードウェア・ファイアウォール (専用)」**または**「ハードウェア・ファイアウォール (高可用性)」**を選択します。 

	高可用性オプションを選択した場合は、同じハードウェアとインターフェースが配備されますが、アクティブ・ノードに障害が発生した場合にトラフィックの処理を続行できるように、第 2 のパッシブ・ノードが配備されます。 高可用性により、過剰なダウン時間のリスクが削減されます。 

5. **「この VLAN 上のサーバー」**ボタンをクリックして、適切な VLAN を選択していることを確認します。
6. 支払方法を入力して、**「続行」**をクリックします。
7. 次の画面で、割引コードを入力し (該当する場合)、マスター・サービス契約を読んで同意し、**「注文」**をクリックします。 
