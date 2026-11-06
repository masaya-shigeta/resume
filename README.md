# 職務経歴書

Webエンジニア(バックエンド中心 / フルスタック)。Go・PHPを軸にフロントエンド・インフラまで担当し、要件定義から保守・運用まで一貫して対応する。

- **Webエンジニア歴** 9年目(2018年4月〜 ※社内SE期間を除く) / **個人事業歴** 7年目(2019年11月〜)
- **言語** Go, PHP, TypeScript / JavaScript
- **フロントエンド** Vue.js, Nuxt
- **インフラ** AWS, GCP

## 自己紹介

|項目|内容|
|:---|:---|
|所属|個人事業主|
|最寄駅|横浜駅|
|年齢|32歳|
|稼働|週5日(+α)|
|学歴|4年制大学卒業|
|資格|普通自動車運転免許|
|GitHub|[@masaya-shigeta](https://github.com/masaya-shigeta)|

WEBエンジニアとして約9年間活動する中で、多くの開発現場に参画させていただくことができました。その中で、未経験分野へのキャッチアップを素早くすることはもちろんですが、何よりコミュニケーションの大切さを実感しています。そのため私自身、常に開発チーム内外でのつながりを意識し、サービスとして良い方向に導くためのエンジニアとしての行動を心がけています。

## 技術スキル

### 言語

<table>
<tr><th align="left" width="150">言語</th><th align="left">経験</th></tr>
<tr><td nowrap><b>Go</b><br>v1.11〜v1.25</td><td>Echo, Gin, Revel, GORM, gorilla/websocket, GraphQL。リアルタイム入札API(WebSocket)の新規構築、マイクロサービスAPI、大規模テナント向けの性能改善</td></tr>
<tr><td nowrap><b>PHP</b><br>v7.0〜v8.0</td><td>Laravel(v5.5〜v8.0), CakePHP。新規サービスの立ち上げから運用保守、テーブル設計から画面までの機能開発</td></tr>
<tr><td nowrap><b>TypeScript / JavaScript</b></td><td>Vue.js, Nuxt(v4)。管理画面・SaaSのフロントエンド開発</td></tr>
<tr><td nowrap><b>Python</b></td><td>Serverless Framework上のAWS Lambda開発</td></tr>
</table>

### インフラ・ミドルウェア

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>AWS</td><td>ECS, Lambda, Cognito, MSK, QLDB, RDS, CloudWatch Logs など</td></tr>
<tr><td nowrap>GCP</td><td>メディア・CMSの開発・運用で利用</td></tr>
<tr><td nowrap>データストア</td><td>MySQL(5.7 / 8.0), PostgreSQL, Microsoft SQL Server, Redis, Amazon QLDB</td></tr>
<tr><td nowrap>CI/CD・コンテナ</td><td>GitHub Actions, Docker / Docker Compose, Serverless Framework, golangci-lint</td></tr>
<tr><td nowrap>監視・負荷試験</td><td>Datadog, k6</td></tr>
<tr><td nowrap>その他</td><td>Microsoft Entra ID, OpenVidu, TreasureData</td></tr>
</table>

### AIツール

Claude Code, GitHub Copilot。Claude Codeのスキルとレビュー基準書を作り、人とAIが同じ基準でPRをレビューする仕組みをCIに組み込んだ実績あり。

## プロジェクト

> - Webエンジニアとして参画したプロジェクトのみ掲載(社内SE時代は[Webエンジニア以前の職歴](#webエンジニア以前の職歴)に記載)
> - 終了日の新しい順

### 1. CO2排出量 可視化SaaS開発 (2023-04 〜 現在)

CO2排出量を可視化するSaaS。機能の実装、認証基盤、新アーキテクチャでのサービス再構築を担当。

**フルスタック(バックエンド・フロントエンド中心)** / 業務委託(フルタイム) / 開発チーム5人(開発部30人・全体150人) / 要件定義〜保守・運用

- 認証サーバーの構築(AWS Cognito単体の構成からの乗り換え)
  - Cognito の preSignUp Lambda と Microsoft Entra ID(object id によるサインイン)をつなぐ認証ブリッジを実装
  - パスワードバリデーション API を実装
  - ログガイドラインを策定し、サービス全体のログレベルとエラー分類を統一
- 新アーキテクチャでのサービス再構築の設計・実装。閉包テーブルを使い、データ階層の深さを表現
- 政府関連データ基盤との API 連携
  - 経産省が推進する Ouranos と連携し、事業所・部品構成・取引関係の情報を登録・更新
  - 省エネ法・温対法の電子報告(EEGS)向けに、法定様式の XML / Excel 出力を33種類実装
- 大規模テナント向けの性能改善
  - 24,000拠点規模を想定し、機能全体のパフォーマンスを改善
  - 拠点の一括取得(最大30,000件)のページング改善
  - 全選択の処理を O(N²) から O(N) に改善
  - 本番のロック競合(約15,000行の CSV 一括更新で Lock wait timeout)について根本原因を特定し、バルク処理を実装
- 自社内の複数プロダクト間のデータ連携(API 開発)
  - マイクロサービスとして契約情報 API とマッピング DB を構築
  - golangci-lint を CI に導入し、テスト用 DB を構築
- AI活用
  - AI による PR レビューの仕組みを構築。Claude Code のスキルとレビュー基準書を作成し、人と AI が同じ基準でレビューする構成にして CI に組み込んだ
  - Datadog のエラーログを週次で自動収集・分類し、AI で分析してレポートにする仕組みをチームで構築・運用。本番障害の調査にも使い、ログ解析から仮説の検証、レポート作成まで効率化した

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>フロントエンド</td><td>Nuxt(v4), GraphQL</td></tr>
<tr><td nowrap>バックエンド</td><td>Go(v1.25), Echo, GraphQL, MySQL, AWS(ECS, Cognito, Lambda など), Microsoft Entra ID, Datadog, GitHub</td></tr>
<tr><td nowrap>AI</td><td>Claude Code, GitHub Copilot</td></tr>
</table>

### 2. BtoBオークションWebアプリ PM・開発 (2024-01 〜 現在)

中古品のBtoBオークションサービス。機能実装、リアルタイム入札基盤の新規構築、性能改善を担当。

**PM / フルスタック(バックエンド中心)** / 業務委託(月40h程度) / 開発チーム10人 / 要件定義〜保守・運用

- Go / WebSocket によるリアルタイム入札APIの新規構築(主担当)
  - Gin・gorilla/websocket・Redis で、入札状況を push 配信するサーバーを一から設計・実装
  - Dockerfile 作成、CloudWatch Logs へのログ転送、GitHub Actions による stg / 本番への自動デプロイまで担当
- 既存の PHP システムと Go API の連携(商品インポートバッチからのデータ連携)
- k6 による WebSocket 負荷試験の仕組みづくり。テストデータ投入CLI、JWT一括生成CLI、試験シナリオを作成し、Makefile のコマンドだけで繰り返し試験できるようにした
- 新機能の設計・実装(CakePHP、テーブル設計から画面まで)。リクエスト・オファー機能、入金管理機能、即決購入機能、保留交渉・再交渉ロジックの作り直し
- 性能改善
  - SQLチューニング(EXISTS サブクエリへの書き換え、取得範囲の限定、インデックス追加)
  - 画像の遅延読み込みによる、リアルタイムオークション画面の表示の軽量化
- チーム共通の開発環境の整備(Docker Compose、MySQL 5.7 → 8.0 への移行)

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>バックエンド</td><td>Go, Gin, Echo, gorilla/websocket, Redis, PHP(CakePHP), MySQL, AWS(ECS, CloudWatch Logs など), Docker, GitHub Actions</td></tr>
<tr><td nowrap>AI</td><td>Claude Code, GitHub Copilot</td></tr>
<tr><td nowrap>その他</td><td>k6(負荷試験)</td></tr>
</table>

### 3. 英語学習Webアプリ立ち上げ (2021-08 〜 2023-12)

英語学習を行えるWebアプリの新規開発と運用・保守。

**フルスタック** / 業務委託(月40h程度) / 開発チーム10人 / 要件定義〜結合テスト

- 設計、サービス開発
- サービススタート段階からリリースまで一貫して対応
- デザイナー・QAチームとの連携

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>フロントエンド</td><td>JavaScript</td></tr>
<tr><td nowrap>バックエンド</td><td>PHP(v8.0), Laravel(v8.0), MySQL, AWS</td></tr>
</table>

### 4. 後払い決済システム台帳管理プラットフォーム開発 (2022-07 〜 2023-03)

複数の後払い決済サービスの台帳を統合管理するプラットフォームの研究開発および実装。

**バックエンド / インフラ** / 業務委託(フルタイム) / 開発チーム4人(全体300人) / 要件定義〜結合テスト

- システムのプロトタイプ開発からインフラ構築
- 技術検討

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>バックエンド</td><td>Go(v1.18), Amazon QLDB, RDS, AWS(ECS, MSK など)</td></tr>
</table>

### 5. 業務プロセス管理システム / 広告媒体素材チェックツール開発 (2020-11 〜 2022-06)

広告領域における業務プロセス管理システム、広告媒体素材チェックツールの新規開発。

**フルスタック** / 業務委託(フルタイム) / 開発チーム8人(全体500人) / 要件定義〜保守・運用

- Serverless Framework による AWS Lambda を含めた環境構築
- サービス新規開発における技術選定
- 外部アクセス向け API 開発による認証・認可

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>フロントエンド</td><td>Vue.js</td></tr>
<tr><td nowrap>バックエンド</td><td>PHP(Laravel), Python, MySQL, AWS(Lambda など), Serverless Framework</td></tr>
</table>

### 6. メディア・CMS開発 (2019-11 〜 2020-10)

金融メディアのCMS開発およびメディアの開発・運用。

**フルスタック** / 業務委託(フルタイム) / 開発チーム15人(全体120人) / 実装〜保守・運用

- メディア運営を通したサービス開発
- ウェビナー機能の開発
- CMS自体の開発

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>フロントエンド</td><td>Vue.js, TypeScript</td></tr>
<tr><td nowrap>バックエンド</td><td>Go(v1.12), PostgreSQL, GCP, OpenVidu</td></tr>
</table>

### 7. LINEを使用したメッセージングアプリ開発 (2019-04 〜 2019-10)

LINE BOT の公式アカウント運用・開発。

**バックエンド** / SES(正社員) / 開発チーム30人(全体300人) / 実装〜保守・運用

- 高トラフィックなサービスの開発を経験し、負荷分散などの実装スキルを習得

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>バックエンド</td><td>Go(v1.12), MySQL, AWS, TreasureData</td></tr>
</table>

### 8. ECプラットフォーム開発 (2018-11 〜 2019-04)

ECサイトを構築できるプラットフォームのスクラッチ開発。

**バックエンド** / SES(正社員) / 全体10人 / 基本設計〜保守・運用

- 汎用性を考えた設計・実装
- Go での実装

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>バックエンド</td><td>Go(v1.11), Revel, GORM, MySQL, AWS</td></tr>
</table>

### 9. CRMツール開発 (2018-04 〜 2018-10)

社内CRMツールの開発と運用保守。

**フルスタック** / 正社員 / 開発チーム15人(全体200人) / 実装〜保守・運用

- 開発未経験から Laravel での開発を習得

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>フロントエンド</td><td>JavaScript</td></tr>
<tr><td nowrap>バックエンド</td><td>PHP(v7.0), Laravel(v5.5), MySQL, AWS</td></tr>
</table>

## Webエンジニア以前の職歴

> Webエンジニア歴には含めていません

### 物流企業での在庫管理システム展開業務(社内SE) (2016-04 〜 2018-03)

社内で利用する物流管理システムの展開と運用保守。

**社内SE** / 新卒入社・正社員 / チーム20人(全体1000人) / 基本設計〜詳細設計

- 国内外の物流現場での要件ヒアリング
- SQL によるデータ調査

<table>
<tr><th align="left" width="150">分類</th><th align="left">技術</th></tr>
<tr><td nowrap>データベース</td><td>Microsoft SQL Server</td></tr>
</table>

<!-- 原本(Google Drive): 経歴書（重田雅也）2026年9月.xlsx -->
