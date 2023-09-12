# 職務経歴書

## 基本情報

|key|value|
|---|---|
|氏名|池田 流弥（いけだ りゅうや）|
|生年月日|1995 年 8 月 29 日|
|現住所|東京都 / 香川県|

---

## 学歴・職歴

|年|月|経歴|
|---|---|---|
|2011|4|香川高等専門学校 情報工学科 入学|
|2016|3|香川高等専門学校 情報工学科 卒業|
|2016|4|香川大学 工学部 電子・情報工学科 編入学|
|2018|3|香川大学 工学部 電子・情報工学科 卒業|
|2018|4|香川大学大学院 工学研究科 信頼性情報システム工学専攻 入学|
|2020|3|香川大学大学院 工学研究科 信頼性情報システム工学専攻 修了|
|2020|4|ヤフー株式会社 入社|
|||在職中|
|2021|7|株式会社 Newro 業務委託 開始|
|2023|1|株式会社 Newro 業務委託 終了|
|2023|7|Alanse 株式会社 業務委託 開始|

### 職務経歴

#### ヤフー株式会社（2020/04〜現在）

広告配信システムの開発・運用に従事。<br>主に以下のシステムのビジネス案件の開発や運用に関わる。

- 広告配信における予算情報・課金を管理する API
- 広告主の広告配信目的に応じた配信最適化を行うバッチ
- vimps 保証広告の vimps シミュレーション・在庫管理 API

|期間|プロジェクト名|業務内容|利用技術|担当業務・役割|
|---|---|---|---|---|
|2020/10 ~ 2021/03|PID 制御によって得られた課金制御情報を連携するバッチの新規開発|広告配信オークションにおいて、入札価格の係数を PID 制御により計算し、オークション価格の計算式に利用することで収益拡大を目指す。<br> PID 制御によって計算された係数を広告検索システムに連携するバッチシステムの設計・開発・運用に従事（上記の配信最適化を行うバッチとは別に開発）。ライブテストにより、最大で 5,000,000 円/day の収益拡大が見込めることを確認|Go, S3, HDFS, Private PaaS|・係数を連携するシステムの設計・開発・運用<br>・関連チームとのコミュニケーション<br>・プロダクトオーナー|
|2020/12 ~ 2021/05|vimps 補償広告の vimps シミュレーション、在庫管理 API・配信制御バッチの開発|Yahoo!広告予約型（Yahoo!JAPAN のトップページなどに視認性の高い画像や動画広告を掲載する広告商品）は viewable impression(vimps)を保証する商品となっている。<br>広告の掲載箇所やターゲティング条件、支払い金額を入力とし、配信可能 vimps を推論するシミュレーション API と実際に vimps を保証するための配信制御バッチの開発・運用に従事。2021/04 のリリースに貢献|Java, Go, SpringBoot, MySQL, Apache Solr, Amazon S3, Apache Cassandra, HDFS, Kong(API Gateway), Private PaaS|・東京 2020 五輪などの大量に vimps が見込めるときのシミュレーション API と配信制御バッチの特殊ロジックの開発<br>・シミュレーション API のマルチ AZ 化<br>|
|2021/04 ~ 2021/09|目的型配信計画バッチのインフラ構成見直し|バッチ処理は複数のストリーム処理と MQ を通じて実施されている。ログ形式変更・ログ量増加によりストリーム処理の最適化が必要であったため、実装を修正した。<br>また、あるストリーム処理についてシステム負荷が大きく、運用が難しくなっていたため、ストリーム処理ではなく一定期間のログを利用した定期的なバッチ処理に置き換えを実施した。ビジネス的な損失なく、運用負荷と大規模なリソース削減（8GB * 180 worker -> 1GB * 2 台の PaaS + 社内共用の MQ という構成に変更）を実現した。|Java, Go, SpringBoot, Apache Cassandra, Apache Storm, Kafka(廃止）, Apache Pulsar , Amazon S3, Private PaaS|・ストリーム処理の実装修正<br>・インフラ構成置き換え作業<br>・インフラを置き換えることでのシステム負荷と移行スケジュールの見積もり|
|2021/09 ~ 2022/05|広告配信における予算情報・課金を管理する API における無停止 RDB 移行|予算情報・課金を管理する API で利用している Oracle12c を Oracle19c に移行する。このサービスが停止すると他サービスの SLO を満たせない、売り上げやお客様への影響が大きいことがわかったため、アプリケーションを停止せず、DB を移行する取り組みを実施。<br />  対応後、社内テックブログに執筆：https://techblog.yahoo.co.jp/entry/2022102430369838/ |Java, SpringBoot, OracleDB, VM, chef, S3, protocol buffer|・Oracle19c での各種パフォーマンス検証<br>・性能面、ビジネス面での技術的負債の解消<br>・ DB マイグレーションのための機能開発<br>・関連チームとのコミュニケーション|
|2022/06 ~ 2022/09|vimps 補償広告の vimps シミュレーションの機能改善|viewable impression(vimps)保証達成精度向上のため、フリークエンシーキャップ（広告を閲覧する回数を指定した期間で固定する機能）を考慮するロジックを追加|Java, SpringBoot, MySQL, Apache Solr, Amazon S3, HDFS, Kong(API Gateway), Private PaaS|・改善後のシミュレーションロジックの設計からリリースまで（設計、実装、性能試験、リリース）|
|2022/10 ~ 2023/03|vimps 補償広告の vimps シミュレーションの機能改善、保守・運用|・ viewable impression(vimps)保証達成精度向上のため、広告配信面によって vimps を保証するためのバッファを変更するロジックの追加<br>・ 広告オーディエンスを OR 検索で指定するようにするための機能拡張（https://ads-promo.yahoo.co.jp/support/release/30406415.html)|Java, SpringBoot, MySQL, Apache Solr, Amazon S3, HDFS, Kong(API Gateway), Private PaaS|・ 改善後のシミュレーションロジック及びオーディエンスの検索条件を変更する案件の設計からリリースまで（外部チームとのコミュニケーション、設計、実装、性能試験、リリース）<br>・ シミュレーションシステムのシステムオーナー|
|2022/12 ~ 現在|広告配信における予算情報・課金を管理する API のコード改善|予算情報・課金を管理する API は度重なる機能追加に伴い、コードの機能追加が難しい状態となっていた。<br>・ 機能改修のしやすいアーキテクチャや実装方針の提案、テストピラミッド・テストレベルを念頭においたテスト方針の提案を実施<br>・2023/04 現在、提案したテスト方針を採用し、レガシーなテストについて刷新が完了。提案した実装方針で一部機能が実装されている状態であるため、全ての機能について実装を刷新中|Java, SpringBoot, OracleDB, kubernetes, Amazon S3, protocol buffer|・ 刷新後の大まかなクラス構成を示したプロトタイプの作成、刷新後のアーキテクチャ・実装方針の提案<br>・ 負債となっていたテストの改善方針をテストピラミッド・テストサイズを考慮して提案、ユニットテスト以外の全てのテストについて刷新完了<br>・ 新機能開発時に刷新後の実装方針で実装できるようサポート<br>・ 既存機能の刷新中|

### 株式会社Newro（2021/07〜2023/01）

英語教育 SaaS システムの開発に従事。<br>現在は 30 名ほどの塾生に利用していただき、システムの効果検証中。

|期間|プロジェクト名|業務内容|利用技術|担当業務・役割|
|---|---|---|---|---|
|2021/07 ~ 2022/01|MVP プロダクトの改修・保守運用|MVP として開発された SaaS システムの保守運用を担当。また、アカウント追加や利用している音声評価 API の切り替えも実施|Python, Django, EC2, Github Actions|・MVP アプリケーションへの Git 管理、CI の導入<br>・オフショアに頼って開発された機能の修正・レビュー<br>・保守運用|
|2021/10 ~ 2023/01|ネイティブアプリへの移管|MVP として開発された SaaS システムの利便性、本格的な開発のため、ネイティブアプリへの移管を実施。エンジニアの副業メンバーは自分を含む 2 名であったため、自分はバックエンドの開発全般を担当。<br>メンバーの少なさからバックエンド、フロントエンドのコンテキストスイッチが発生しない TypeScript をメインの言語として採用|TypeScript, Nest.js, Prisma, Go, Docker, Aurora MySQL, ECS, CodeDeploy, Lambda, Amazon API Gateway, GitHub Actions, Terraform|・ネイティブアプリ用の Web API の設計・開発・運用全て<br>・Web API への Ci/CD の導入<br>・アプリケーションが利用するリソースの IaC|
|2022/02 ~ 2023/01|ネイティブアプリの機能追加・デザイン改修|ネイティブアプリ側で実現したい要件が増えたため、ネイティブアプリの機能・デザイン改修に従事。2023/01 にサービスクローズ|TypeScript, React Native, React-Hooks-Form, Zeplin|

## Alanse 株式会社

業務委託として、他社の Web アプリケーション開発に関わる。  
主にバックエンドアプリケーションの開発、 Terraform + AWS によるインフラ構築、CI/CD パイプラインの構築、システムアーキテクチャの設計などを担当。

---

## 技術スタック

### 言語

- Java
- Go
- Python
- TypeScript

### フレームワーク

- SpringBoot
- Apache Storm
- React・Next.js
- Nest.js

### インフラ・その他

- MySQL・OracleDB
    - 実行計画から SQL のチューニングの実施（OracleDB）
    - インデックスの改善（OracleDB）
    - DB 移行の経験あり（OracleDB）
- AWS
  - IaC を使って WebAPI に必要な一通りのインフラを構築できる程度。業務では利用していないため、AWS 上のインフラチューニングなどは不得意
- Terraform・Terragrunt
  - 主に業務委託で利用
  - AWS で ECS や RDS(Aurora MySQL), DynamoDB, Athena などを活用したインフラ構成ができる程度
- PagerDuty
  - 本業でチームの架電ローテーションの検討・運用

---

## 連絡先・各種アカウント

|項目|値|
|---|---|
|メールアドレス|tech.adeki@gmail.com|
|Github|[rikeda71](https://github.com/rikeda71)|
|twitter|[rikeda71](https://twitter.com/rikeda71)|
|Zenn|[rikeda71](https://twitter.com/ikechan0829)|

---

## 課外活動

### OSS

- [TorchCRF](https://github.com/s14t284/TorchCRF)：Conditional Random Fields の pytorch 1.0 対応
- [miNER](https://github.com/s14t284/miNER)：固有表現抽出の実験結果を簡単に評価できるライブラリ
- [foggo](https://github.com/s14t284/foggo)：Go の 構造体定義から Functional Options Pattern のコードを自動生成する CLI ツール
- [virtual-pilgrimage](https://github.com/sports-club-hanzan/virtual-pilgrimage)：仮想的に四国八十八ヶ所お遍路を体験できる歩数系アプリ。地方自治体から依頼され、開発したアプリケーション

### 執筆歴

- [サービス無停止でRDB移行 〜 Yahoo!広告のOracleDB移行事例 ・ Yahoo! JAPAN Tech Blog](https://techblog.yahoo.co.jp/entry/2022102430369838/)
- [ECS Fargate上で公開しているPrometheus形式のメトリクスをDatadogのカスタムメトリクスとして登録するまで](https://zenn.dev/ikechan0829/articles/dd_custom_metrics_ecs_fargate)
- [Go の 構造体定義から Functional Options Pattern のコードを自動生成する CLI ツールを作った・Zenn](https://zenn.dev/ikechan0829/articles/foggo_generate_fop_cli)
- [24時間で漫画みたいにニュースを読めるアプリを開発した話 ・ Yahoo! JAPAN Tech Blog](https://techblog.yahoo.co.jp/entry/2020071630011382/)
- [Extraction of Food Product and Shop Names from Blog Articles Using Named Entity Recognition](https://link.springer.com/chapter/10.1007/978-981-15-6168-9_37)
  - Pacling2019(acceptance rate: 40-50%)
  - 上記論文を含む査読あり国際学会 2 件、査読なし国内学会 8 件に投稿・発表

### 資格・賞歴

|年|概要|
|---|---|
|2020|特に優れた業績による返還免除（全額）, 日本学生支援機構|
|2019|2019 年度 香川大学大学院 特待生|
|2017|2017 年度 香川大学 特待生|
|2016|応用情報技術者試験 合格|
