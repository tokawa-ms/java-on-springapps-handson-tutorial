# 「触ってわかる Java on Azure Spring Apps 」ハンズオン セミナー

## 目標
今回のハンズオンは、参加者が本ハンズオンで得た知識をご自身のアプリケーションに応用できるようになります。 

## 対象となるお客様
- アプリケーション開発者
- インフラストラクチャ アーキテクト

## 全体概要

- **演習 1**

    1. Spring Boot アプリケーション接続用の MySQL データベースを　Azure 上作成
    1. アプリケーションのプロジェクトを Visual Studio Code 拡張の機能を使用してコンテナ化し、ローカル実行
    1. IaC(ARM テンプレート) を使用した Azure リソース ( Azure Spring Apps 等) のデプロイ 
    1. アプリケーションを Azure Spring Apps にデプロイ ( 方法は以下のどちらかを選択 )
       - Azure ポータルサイト経由手動でデプロイ
       - Azure CLI を使ってデプロイ
    1. Azure Spring Apps にデプロイ完了後、Web ブラウザーでアクセスして動作確認<br><br>
    
- **演習 2**
    1. GitHub Actions を使用したアプリケーションのデプロイワークフローの作成 
    1. GitHub Actions を使用した CI/CD 環境の作成
    1. 作成したデプロイワークフローで Blue/Green リリースの実施
    1. Azure Spring Apps の監視・ログ確認
    1. Azure Spring Apps のスケーリング



## アーキテクチャ

- **アーキテクチャ図**

  ![Handson architecture](./images/common-architecture.png)

<br>

## 事前準備

1. [事前準備](./steps/Common.md)

## 操作手順

- **演習 1**

  1. [ローカル環境でのプロジェクトの実行](./steps/P1-01.md)
  1. [Dockerfile の追加](./steps/P1-02.md)
  1. Docker イメージの作成と  Azure Container Registry への Push (**以下どちらか選択する**)
      1. [Azure Container Registry に直接 Docker イメージを作成する演習](./steps/P1-03-a.md)
      1. [ローカル環境で Docker イメージを生成する演習](./steps/P1-03-b.md)
  1. [Azure Container Apps の作成とコンテナーアプリのデプロイ](./steps/P1-04.md)
>
- **演習 2**
  
  - [準備: Azure リソースを作成](./steps/P2-00.md)

  1. **API アプリ**  
     演習 1 で作成した **API アプリのリポジトリ**に対して、以下の演習を実施し、GitHub Actions を使用したアプリケーションのデプロイワークフローを作成 

     1. [GitHub アクション雛形を作成](./steps/P2-01.md)
     1. [Azure Container Registry の接続情報を追加](./steps/P2-02.md)
     1. [Azure Container Registry にコンテナーイメージ作成処理を追加](./steps/P2-03.md)
     1. [Deploy ジョブを追加](./steps/P2-04.md)
     1. [Azure 接続処理を追加](./steps/P2-05.md)
     1. [Azure Container Apps にアプリをデプロイする処理を追加](./steps/P2-06-a.md)
     1. [CI/CD を体験](./steps/P2-07-a.md)<br><br>

  1. **UI アプリ**  
     演習 1 で作成した **UI アプリのリポジトリ**に対して、以下の演習を実施し、GitHub Actions を使用したアプリケーションのデプロイワークフローを作成 

     1. 上記 **API アプリ**の a〜e の手順を同様に実施
     1. [Azure Container Apps にアプリをデプロイする処理を追加](./steps/P2-06-b.md)
     1. [CI/CD を体験](./steps/P2-07-b.md)<br><br>     

- **(Option) リソースのクリンアップ**
このハンズオンで作成した Azure リソースのプロビジョニングを解除する場合は以下の手順を実施

  1. すべての Azure ソース グループを削除

      - ポータルからリソース グループのブレードに移動し、画面上のコマンド バーで `[Delete (削除)]` を選択

      - リソース グループの名前を再度入力して `[Delete (削除)]` を選択し、削除の確認

  2. 「演習 2」の「5. Azure 接続処理を追加」で作成したサービス プリンシパルを削除

<br>

---
## LICENSE

このドキュメントに記載されている情報 (URL や他のインターネット Web サイト参照を含む) は、将来予告なしに変更することがあります。別途記載されていない場合、このソフトウェアおよび関連するドキュメントで使用している会社、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、出来事などの名称は架空のものです。実在する商品名、団体名、個人名などとは一切関係ありません。お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いいたします。著作権法による制限に関係なく、マイクロソフトの書面による許可なしに、このドキュメントの一部または全部を複製したり、検索システムに保存または登録したり、別の形式に変換したりすることは、手段、目的を問わず禁じられています。ここでいう手段とは、複写や記録など、電子的、または物理的なすべての手段を含みます。

マイクロソフトは、このドキュメントに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の知的財産権に関する権利をお客様に許諾するものではありません。

製造元名、製品名、URL は、情報提供のみを目的としており、これらの製造元またはマイクロソフトのテクノロジを搭載した製品の使用について、マイクロソフトは、明示的、黙示的、または法令によるいかなる表明も保証もいたしません。製造元または製品に対する言及は、マイクロソフトが当該製造元または製品を推奨していることを示唆するものではありません。掲載されているリンクは、外部サイトへのものである場合があります。これらのサイトはマイクロソフトの管理下にあるものではなく、リンク先のサイトのコンテンツ、リンク先のサイトに含まれているリンク、または当該サイトの変更や更新について、マイクロソフトは一切責任を負いません。リンク先のサイトから受信した Web キャストまたはその他の形式での通信について、マイクロソフトは責任を負いません。マイクロソフトは受講者の便宜を図る目的でのみ、これらのリンクを提供します。また、リンクの掲載は、マイクロソフトが当該サイトまたは当該サイトに掲載されている製品を推奨していることを示唆するものではありません。

Copyright (c) Microsoft Corporation. All rights reserved.
