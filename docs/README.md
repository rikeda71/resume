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
| 2011 | 4 | 香川高等専門学校 情報工学科 入学 |
| 2016 | 3 | 香川高等専門学校 情報工学科 卒業 |
| 2016 | 4 | 香川大学 工学部 電子・情報工学科 編入学 |
| 2018 | 3 | 香川大学 工学部 電子・情報工学科 卒業 |
| 2018 | 4 | 香川大学大学院 工学研究科 信頼性情報システム工学専攻 入学 |
| 2020 | 3 | 香川大学大学院 工学研究科 信頼性情報システム工学専攻 修了 |
| 2020 | 4 | [ヤフー株式会社](https://about.yahoo.co.jp/) 入社 |
| 現在 ||[LINEヤフー株式会社](https://www.lycorp.co.jp/) 在職中 |
||||
|2021|7|株式会社 Newro 業務委託 開始 |
|2023|1|株式会社 Newro 業務委託 終了 |
|2023|7|[Alanse 株式会社](https://www.alanse.co.jp/) 業務委託 開始 |

## 職務経歴

### LINE ヤフー株式会社(2023/10 ~ 現在), ヤフー株式会社（2020/04 ~ 2023/09）

広告配信システムの開発・運用に従事。<br>主に以下のシステムのビジネス案件の開発や運用に関わる。

- 広告配信における予算情報・課金を管理する API (2020/10 ~)
- 広告主の広告配信目的に応じた配信最適化を行うバッチ (2020/10 ~)
- vimps 保証広告の vimps シミュレーション・在庫管理 API (2020/10 ~)

また、会社合併後はデータサイエンティストの部署に兼務が付き、下記の案件にも並行して携わっている。

- vimps 保証広告の配信制御 Workflow (2023/10 ~)
- 広告配信システムの MLOps・機械学習に関する課題改善 (2024/01 ~)
- 機械学習エンジニアのための補助ツール開発 (2024/04 ~)

代表的なプロジェクトについて下記に記す。

#### PID 制御によって得られた課金制御情報を連携するバッチの新規開発

| | |
| -- | -- |
| 期間 | 2020/10 ~ 2021/03 |
| 職種 | バックエンドエンジニア |
| 役割 | プロダクトオーナー |
| 業務内容 | 広告配信オークションにおいて、入札価格の係数を PID 制御により計算し、オークション価格の計算式に利用することで収益拡大を目指す。<br> PID 制御によって計算された係数を広告検索システムに連携するバッチシステムの設計・開発・運用に従事（上述の「配信最適化を行うバッチ」とは別に開発）。<br>ライブテストにより、最大で 数百万円/day の収益拡大が見込めることを確認。<br> PoC のシステムであったため、昨日は他システムに移管 |
| 利用技術 | Go, Amazon S3, HDFS, Private PaaS |
| 担当業務 | ・係数を連携するシステムの設計・開発・運用<br>・関連チームとのコミュニケーション |

#### vimps 補償広告の vimps シミュレーション、在庫管理 API・配信制御バッチの開発

| | |
| -- | -- |
| 期間 | 2020/12 ~ 現在 |
| 職種 | バックエンドエンジニア |
| 役割 | メンバー、プロダクトオーナー(2022/10 ~) |
| 業務内容 | Yahoo!広告 の viewable impression(vimps)を保証する商品を実現するため、下記のシステムの開発・保守に従事。 <br> - 広告の掲載箇所やターゲティング条件、支払い金額を入力とし、配信可能 vimps を推論するシミュレーション API <br> - vimps を保証するための配信制御バッチ <br> 2021/04 のリリース時の機能開発、 vimps 保証達成精度向上のためのフリークエンシーキャップを考慮したロジック改善、[広告オーディエンスを OR 検索で指定するようにするための機能拡張](https://ads-promo.yahoo.co.jp/support/release/30406415.html) に従事。 |
| 利用技術 | Java, Go, SpringBoot, MySQL, Apache Solr, Amazon S3, Apache Cassandra, HDFS, Kong(API Gateway), Private PaaS |
| 担当業務 | ・係数を連携するシステムの設計・開発・運用<br>・関連チームとのコミュニケーション |

#### 広告主の広告配信目的に応じた配信最適化を行うバッチのインフラ構成改善

| | |
| -- | -- |
| 期間 | 2021/04 ~ 2021/09 |
| 職種 | バックエンドエンジニア |
| 役割 | メンバー |
| 業務内容 | 本バッチ処理は複数のストリーム処理から MQ を通じて受け取った Message を Consume するシステム構成であった。<br>この処理はログ量などの問題からシステム負荷が大きく、運用が難しくなっていたため、ストリーム処理ではなく一定期間のログを利用したマイクロバッチに置き換えを実施した。 <br> ビジネス影響を与えず、運用負荷および大規模なリソースの削減（8GB * 180 worker -> 1GB * 2 台の k8s CronJob + 社内共用の MQ という構成に変更）を実現した。<br> また、別途運用しているストリーム処理についても実装を修正することでログ量増加に対応できるようにした。|
| 利用技術 | Java, Go, SpringBoot, Apache Cassandra, Apache Storm, Apache Kafka (廃止）, Apache Pulsar, Amazon S3, Kubernetes |
| 担当業務 |・インフラ構成置き換え作業<br>・インフラを置き換えることでのシステム負荷と移行スケジュールの見積もり<br>・ストリーム処理の実装修正|

#### 広告配信における予算情報・課金を管理する API における無停止 RDB 移行

詳細は以下のリンク参照。

- [サービス無停止でRDB移行 〜 Yahoo!広告のOracleDB移行事例 ・ Yahoo! JAPAN Tech Blog](https://techblog.yahoo.co.jp/entry/2022102430369838/)
- [RDB無停止移行への挑戦 #データベース_findy](https://speakerdeck.com/rikeda71/rdbwu-ting-zhi-yi-xing-henotiao-zhan-number-detabesu-findy)

| | |
| -- | -- |
| 期間 | 2021/09 ~ 2022/05 |
| 職種 | バックエンドエンジニア |
| 役割 | メンバー |
| 業務内容 | 予算情報・課金を管理する API で利用している Oracle12c をハードウェア・ソフトウェアの EOL の観点から Oracle19c に移行した。<br> API が停止すると他システムの SLO を満たせない、売り上げやお客様への影響が大きいことがわかったため、アプリケーションを機能を停止させず、DB を移行する取り組みを実施。|
| 利用技術 | Java, SpringBoot, OracleDB, Kubernetes, Amazon S3, Protocol Buffer |
| 担当業務 | ・Oracle19c での各種パフォーマンス検証<br>・移行に伴う性能面、ビジネスロジックの側面での技術的負債の解消<br>・DB マイグレーションのための機能開発<br>・関連チームとのコミュニケーション |

#### 広告配信における予算情報・課金を管理する API のコードベース刷新

| | |
| -- | -- |
| 期間 | 2022/12 ~ 2023/11 |
| 職種 | バックエンドエンジニア |
| 役割 | プロジェクトリード |
| 業務内容 | 予算情報・課金を管理する API は度重なる機能追加に伴い、コードの機能追加が難しい状態となっていた。この状態が継続していたことで、しばらくこの API に関わるビジネス仕様の改善ができていない状態が継続していた。<br>API のソースコードのほとんどを刷新し、ビジネス仕様の改善に取り組める状態を構築した。<br>下記をチームメンバーに提案し、プロジェクトを推進した。<br>・機能改修のしやすいソフトウェアアーキテクチャや実装方針の提案<br>・テストピラミッド・テストレベルを念頭においたテスト方針 |
| 利用技術 | Java, SpringBoot, OracleDB, Kubernetes, Amazon S3, Protocol Buffer |
| 担当業務 | ・旧コードベースの課題の洗い出し、改善案の提案<br>・負債を生みづらくするためのコーディングの教育<br>・実装および実装の分担<br>・他プロジェクトでの実装方針採用のサポート |

#### 広告配信における予算仕様変更

[仕様変更の内容](https://ads-developers.yahoo.co.jp/ja/ads-api/announcement/230140.html)

| | |
| -- | -- |
| 期間 | 2023/07 ~ 2023/12 |
| 職種 | バックエンドエンジニア, 企画 |
| 役割 | メンバー |
| 業務内容 | 自社の広告配信システムの予算仕様を他システム(Google, 旧LINE, 自社の検索広告 etc...) と同様に柔軟に予算が利用できるように改善した。<br>本改善により、広告主視点で他社と仕様が近いことによるユーザビリティ向上・売上の改善を実現した。|
| 利用技術 | Java, SpringBoot, OracleDB, Kubernetes, Amazon S3, Protocol Buffer |
| 担当業務 | ・他社仕様の洗い出し、研究<br>・システム設計<br>ビジネスロジックの実装 |

#### vimps 保証広告の配信制御 Workflow 刷新

| | |
| -- | -- |
| 期間 | 2023/12 ~ 2024/03 |
| 職種 | バックエンドエンジニア, データサイエンティスト |
| 役割 | メンバー |
| 業務内容 | Talend で稼働していた Workflow を Airflow で稼働させるように刷新した。 |
| 利用技術 | Python, Apache Airflow, HiveQL, PySpark |
| 担当業務 | ・集計Workflowの実装・集計結果のマイグレーション<br>・データサイエンティストへのバックエンドエンジニアでの知見の共有(CI/CD, Linter, デザインパターンを利用した実装の改善など) |

#### 機械学習モデルの素性をリアルタイムに収集するストリーム処理基盤の構築

| | |
| -- | -- |
| 期間 | 2024/05 ~  現在 |
| 職種 | バックエンドエンジニア |
| 役割 | プロジェクトリード |
| 業務内容 |  |
| 利用技術 | Apache Flink(予定) |
| 担当業務 |  |

#### 機械学習エンジニアのための補助ツール開発のリード

| | |
| -- | -- |
| 期間 | 2024/05 ~  現在 |
| 職種 | リーダー(育休になったマネージャーの代理であるため、人事的なマネージャーではない) |
| 役割 | リーダー |
| 業務内容 |  |
| 利用技術 | Java, Python, SpringBoot, MySQL, Streamlit, Hive, Trino (予定) |
| 担当業務 |  |

### 株式会社Newro（2021/07〜2023/01）

英語教育 SaaS システムの開発に従事。<br>30 名ほどの塾生に利用していただき、システムの効果検証を行なった。

#### MVP プロダクトの改修・保守運用

| | |
| -- | -- |
| 期間 | 2021/07 ~ 2022/01 |
| 職種 | フルスタックエンジニア |
| 役割 | Dev Lead |
| 業務内容 | MVP として開発された SaaS システムの保守運用を担当。また、アカウント追加や利用している音声評価 API の切り替えも実施。 |
| 利用技術 | Python, Django, EC2, Github Actions |
| 担当業務 | ・MVP アプリケーションへの Git 管理、CI の導入<br>・オフショアに頼って開発された機能の修正・レビュー<br>・保守運用 |

#### MVPプロダクトのネイティブアプリへの移管

| | |
| -- | -- |
| 期間 | 2021/10 ~ 2023/01 |
| 職種 | バックエンドエンジニア, ネイティブアプリエンジニア |
| 役割 | Dev Lead |
| 業務内容 | MVP として開発された SaaS システムの利便性、本格的な開発のため、ネイティブアプリへの移管を実施。エンジニアの副業メンバーは自分を含む 2 名であったため、1人でバックエンドの開発全般を担当。<br>メンバーの少なさからバックエンド、フロントエンドのコンテキストスイッチが発生しない TypeScript をメインの言語として採用。<br>補助的にネイティブアプリへの機能追加・デザイン改修にも従事。2023/01 にサービスクローズ |
| 利用技術 | TypeScript, Nest.js, React Native, Docker, Amazon Aurora MySQL, Amazon ECS, AWS CodeDeploy, AWS Lambda, Amazon API Gateway, GitHub Actions, Terraform |
| 担当業務 |・ネイティブアプリ用の Web API およびクライアントアプリの設計・開発・運用<br>・Web API への Ci/CD の導入<br>・アプリケーションが利用するリソースの IaC |

### Alanse 株式会社（2023/07〜現在）

業務委託として、他社の Web アプリケーション開発に関わる。  
主にバックエンドエンジニアとしてアプリケーションの開発、 Terraform + AWS によるインフラ構築、CI/CD パイプラインの構築、システムアーキテクチャの設計などを担当。

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

### インフラ

- MySQL・OracleDB
    - 実行計画から SQL のチューニングの実施（OracleDB）
    - DB 移行の経験あり（OracleDB）
- Kubernetes
- Apache Solr
- Apache Cassandra
- AWS
   - IaC を使って WebAPI に必要な一通りのインフラを構築できる程度。業務では利用していないため、AWS 上のインフラチューニングなどは不得意
- Terraform・Terragrunt
- PagerDuty
    - 本業でチームのオンコールローテーションの検討・運用
    - 無駄なアラートを自主的に減らす取り組みを実施し、チームの深夜帯・休日のオンコール対応の頻度を改善

### その他

- レガシーコード刷新の経験から、自動テストの整備やソフトウェアアーキテクチャを意識した実装が得意です
- RDB 無停止移行やオンコールローテーションの構築、チームで DevOps を意識して仕事をしていることから、サーバーサイドに関する周りの開発から運用、性能改善まで携わることができます
- 総じて、保守性の高いシステムを構築することに長けています
- データサイエンス組織に属していること、データサイエンティストと共同して仕事をする機会が多いこと、過去に自然言語処理の研究をしていたことより、機械学習やデータ分析にも関心があります。ボトムアップでデータ分析してロジックの改善に取り組むこともあります
- これらの経験より、MLOps に関心があります。バックエンドエンジニアとしての経験を活かした MLOps 基盤の構築に興味があります

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

### 執筆・対外発表歴

- [データベース移行のウラガワ- 円滑なリリースのために取り組んだLT](https://findy.connpass.com/event/294868/.com/rikeda71/rdbwu-ting-zhi-yi-xing-henotiao-zhan-number-detabesu-findy)
    - 発表内容：[サービス無停止でRDB移行 〜 Yahoo!広告のOracleDB移行事例 ・ Yahoo! JAPAN Tech Blog](https://techblog.yahoo.co.jp/entry/2022102430369838/)
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
