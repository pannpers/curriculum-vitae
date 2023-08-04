# Curriculum Vitae


<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [Curriculum Vitae](#curriculum-vitae)
  - [1. Basic Information](#1-basic-information)
  - [2. Overview](#2-overview)
  - [3. Employment History / Work Experience](#3-employment-history--work-experience)
    - [株式会社ZEALS (2019.08 - 2023.04)](#株式会社zeals-201908---202304)
      - [Responsibilities](#responsibilities)
    - [株式会社Voicy (2017.10 - 2019.07)](#株式会社voicy-201710---201907)
      - [Responsibilities](#responsibilities-1)
    - [楽天株式会社 トラベル事業部 (2011.04 - 2017.09)](#楽天株式会社-トラベル事業部-201104---201709)
      - [Responsibilities](#responsibilities-2)
  - [4. Education](#4-education)
        - [関西学院大学 商学部 (2007 - 2011)](#関西学院大学-商学部-2007---2011)
        - [Natural Language](#natural-language)
  - [5. Key Skills](#5-key-skills)
    - [Application Development](#application-development)
      - [Frontend](#frontend)
      - [Backend](#backend)
      - [Architecture Design](#architecture-design)
      - [API Design](#api-design)
      - [Database](#database)
      - [CI/CD](#cicd)
      - [Others](#others)
    - [Infrastructure](#infrastructure)
      - [Cloud Provider](#cloud-provider)
    - [Development Tools](#development-tools)

<!-- /code_chunk_output -->


## 1. Basic Information

| Key | Value |
|---|---|
| Name | 濱田恭匡 (Yoshimasa Hamada) |
| Location | 福岡 |
| Birthday | 1988.07.29 |
| Email | pepperoni9@gmail.com |
| Medium | [@yoshimasahamada](https://medium.com/@yoshimasahamada) |
| Qiita | [pannpers](https://qiita.com/pannpers)
| Twitter | [@panchan9](https://twitter.com/panchan9) |


## 2. Overview
Webアプリケーションのフロントからバックエンドに加え、インフラまで含めた一気通貫でのシステム設計・開発が得意。
プロダクトの初期フェーズはFirebaseやCloud Runなどを使ったサーバーレス開発でスピードを重視しつつ、規模拡大に応じてgRPCとKubernetesを使った、拡張性やスケーラビリティの高いシステムアーキテクチャを構築できる。

バックエンドについては、Clean ArchitectureをベースにしたGoのAPIサーバーやマイクロサービスの開発経験が豊富。

フロントエンドについては、JavaScriptのSPAフレームワーク [Aurelia](https://aurelia.io/) を使ったWebアプリケーション開発が得意。変更に強く、メンテナンス性の高いコードを重視しており、TypeScriptとDI（Dependency Injection）を好む。
また、Web標準へも積極的に追従しており、WebComponentsやブラウザのAPI実装状況などにアンテナを張っている。


## 3. Employment History / Work Experience

### 株式会社ZEALS (2019.08 - 2023.04)
#### Responsibilities
- LINEやFacebookなどの公開API向けのメッセージ配信システムの設計・開発・運用。
  - サービス初期にPythonで開発されたメッセージ配信システムを、Goを採用したマイクロサービス化し、サービスの可用性と拡張性を向上。
  - gRPCによるサービス間通信を実装し、マイクロサービスに求められるTraceabilityを[OpenTelemetry](https://opentelemetry.io/)を用いて実現。
  - データストアとして、Google Cloud SQL（MySQL、PostgreSQL）やRedisを採用。
- GCP上のクラウドリソースやモニタリングシステムの設計・運用。
  - 全アプリケーションが稼働しているKubernetesクラスターの設計・運用。
  - Kubernetes上のワークロードの特性に応じた、適切なリソース選定とManifestのコード管理。
  - 各種GCPリソース（VCP network, DNS, Load Balancer, Storage, PubSub, SQL, etc）の設計、および[Pulumi](https://www.pulumi.com/)を使用した、Infrastructure as Code（IaC）。
  - Datadogを使用し、アプリケーションの異常を検知しSlackへアラートを送信するモニタリングシステムの構築。

### 株式会社Voicy (2017.10 - 2019.07)
#### Responsibilities
- 音声信号処理APIの開発・運用。
  - 音声信号処理のライブラリが充実しているため、言語はPythonを選択。
  - 高速でシンプルなRESTful APIフレームワークのFalconを採用。
- 社内向け管理画面の開発・運用。
  - フロントエンドはSPAフレームワークのAureliaとTypeScriptで開発。
  - バックエンドはGoでRESTful APIを開発。
  - 実行環境はGKE上にKubernetesクラスターを構築。
- 既存のVoiceメディアサービスのバックエンドのリプレイス。
  - 複数のAPIサーバー（toC、toB、社内向け管理画面など）が同じようなドメインロジックを持つようになってきたため、メンテナンスコストの低減を狙い、リプレイスプロジェクトを発足。
  - 詳しい経緯や概要については[Voicy Engineering Blog](https://link.medium.com/cEwQh0ujGY)を参照。
  - ドメインロジックを集約する『共通API』と各クライアントアプリとの橋渡しをする『BFF』の構成で設計。
  - 共通APIをClean ArchitectureをベースにGoで開発。
  - クライアントも含めて、サービス間通信はgRPCに統一し、Type-Safeかつ効率的な開発を実現。
  - 各サーバーごとのDockerコンテナを作成し、オーケストレーションはKubernetesを採用。
  - ローカルマシンでのKubernetes開発環境やCircleCIを使ったCI/CDフローを構築。

---

### 楽天株式会社 トラベル事業部 (2011.04 - 2017.09)
#### Responsibilities
- Data Warehouse (DWH) の開発・運用。
  - オンライン予約サービスで生成されるログやデータベースのレコードを、分析用のDWHへETL処理を行う。扱うデータの種類は、国内外のホテルや航空券、バス、レンタカーと多岐に渡る。
  - DWH製品はTeradata Database（公開済み情報）。
  - 習得技術はSQLとETLジョブを制御するためのShell Script。特に、SQLに関しては、可読性を保ちつつ、大規模データを効率的に処理することが求められていた。
  - DWH内のデータにビジネスサイドがクエリを実行するためのBIツールを保守。
- データ抽出依頼の対応、およびチームマネジメント。
  - BIツールでは抽出できない複雑なデータをSQLを書いて抽出する業務を担当。
  - 3名程度のチームでリーダーとして全体のスケジュール管理なども担当。
- テクニカルサポート。
  - バグや仕様調査などの問い合わせ対応を担当。
  - 大部分のアプリケーションはJavaで書かれており（公開済み情報）、コードを読んで調査を行うケースが多い。




## 4. Education

##### 関西学院大学 商学部 (2007 - 2011)
管理会計を専攻。企業経営を取り巻く様々な数値データから、戦略的な意思決定を行う手法を学ぶ。管理会計を通して、会計知識以外にもマーケティング、経営学、ファイナンスなどに触れる。



##### Natural Language

| Language | Level |
|---|---|
| Japanese | ネイティブ |
| English | 読み書きやチャット、日常会話は問題無し。TOEIC 795点 |


## 5. Key Skills

### Application Development

#### Frontend
- HTML
- CSS
- JavaScript
  - ECMA Script
  - TypeScript
- Framework
  - Aurelia
  - Angular
- PWA (Progressive Web App)

#### Backend
- Golang
  - Framework
    - Echo (REST API)
  - ORM
    - SQL Boiler
    - xorm
  - Testing
    - testify
- Python
  - Version: 2.7 / 3.5-8
  - Framework
    - Falcon
  - Machine Learning
    - pandas
    - scikit-learn
    - Jupyter Notebook
      - JupyterHub
      - JupyterLab

**Note:** 機械学習系のライブラリは少し触れる程度

#### Architecture Design
- Clean Architecture

#### API Design
- gRPC
  - Protocol Buffers
- Open API Specification (Swagger)

#### Database
- RDBMS
  - PostgreSQL
  - MySQL
  - Oracle Database
- KVS
  - Redis
- Document DB
  - Firestore
- Graph DB
  - Neo4j
- Data Warehouse
  - BigQuery
  - Teradata Database

#### CI/CD
- CircleCI
- Cloud Build
- GitHub Actions

#### Others
- WebRTC
- Audio Signal Processing
  - Loudness Normalization
  - Spectral Subtraction
  - Software
    - FFmpeg
    - Sox
<!-- - UX Design -->
  <!-- - Information Architecture -->


---

### Infrastructure
- Docker
- Kubernetes
  - kustomize
  - Skaffold
  - cert-manager \
  (issue and update certificate of Let's Encrypt in k8s)
- Load Balancer / Reverse Proxy
  - Traefik
  - Nginx


#### Cloud Provider
- GCP
  - GKE
  - Cloud Pub/Sub
  - Cloud NAT
  - Cloud DNS
  - Cloud SQL
  - Cloud Storage
  - Firebase
    - Hosting
    - Authentication
    - Firestore
    - Functions
- AWS
  - ECS
  - SNS
  - S3


---

### Development Tools
- Code Editor
  - VS Code
  - Vim
- Git Repository Hosting Service
  - GitHub
  - Bit Bucket
- ITS (Issue Tracking System)
  - Asana
  - JIRA
  - Trello
- Documentation Service
  - Docbase
  - Confluence
  - Scrapbox
- Chat Service
  - Slack
  - Chatwork

