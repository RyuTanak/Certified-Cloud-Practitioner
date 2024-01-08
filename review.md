### 監視系サービス  

- CloudWatch  
  AWSにホストされたアプリケーションのモニタリングサービス  
- CloudTrail  
  ユーザーのアクセスログとAPIのログ取得と監視  

- AWS Config  
  AWSリソースの設定を評価・監視・審査  
- AWS System Manager  
  インフラストラクチャを可視化し、制御  

### EC2の料金体系  

- オンデマンドインスタンス  
  使った分だけインスタンス  
- リザーブドインスタンス  
  1年or3年の利用  
  (リザーブド→予約などの意味)  

- スケジュールドリザーブドインスタンス  
  定期的な利用インスタンス  
  →毎週金曜日10～12時など  
  ※現在は利用停止  

- スポットインスタンス  
  オンデマンドよりも安く済む。一時的な利用に向いている  

- Dedicated Host  
  サーバーを物理的に占有したいとき  
  セキュリティ面で必要な場合に使う  
  (Dedicated→占有などの意味)  

- EC2 Instance Saving Service  
  1年or3年でコスト最適化される契約をする  

### ストレージサービス  

- EBS(Elastic Block Store)  
  EC2のストレージサービス  
  「自動バックアップの有効化」「データ保護の有効化」という機能は存在しない（ひっかけ）  
  あるのはスナップショットで、増分のみ保存される（変更点だけ保存される）  
  →スナップショットの保存先は**S3**である  

- EFS(Elastic File System)  
  NASのように利用可能なファイルストレージ  
  インターネットからはアクセスできない→完全な内部サーバ向けの共有ファイルストレージとなる  
  S3も複数インスタンスからの接続が可能だが、インターネットからのアクセスができる  
  EBSはインターネットからアクセスできないが、複数共有ができない  

- Amazon S3 Glacier  
  S3も複数インスタンスからの接続が可能だが、データアーカイブ用である
  →頻繁に使わないデータを別のディスクに長期保存  

- NAS(一般用語)  
  Network Attached Storage  
  ネットワークに接続されているストレージのこと。ネットワーク上にいるユーザーで共有できる  



### データベースサービス  

- ElastiCache  
  インメモリのDB  
  →メモリ（RAM）上でデータベースの構築保存を行うので、スピードが速い  
  電源を切るときや再起動時に、定期的にストレージにデータを保存している  
  ちなみに、NoSQLである  

- Aurora for MySQL  
  デフォルトで自動バックアップを行う  

- DynamoDB  
  デフォルトで自動バックアップは行わない  

- RedShift  
  リレーショナルデータベース  
  データウェアハウス用なので、主に業務の分析するためのデータの保存に使われる  

  ※Amazon EMRはデータベースではない  
  大量のデータを迅速に処理するためのサービス  

  
### メッセージングサービス  

- SNS  
  Push方式→任意のタイミングで送る（受け取り側は常時受け取り状態）  
- SQS  
  Pull方式→受け取り側がくれと言ったらもらう  
- SES  
  メール  

### 稼働率の話  

- MTBF(Mean Time Between Failure)  
  故障と故障の間の平均時間  
- MTTR(Mean Time To Repair)  
  修復のための平均時間  

```
稼働率 ＝ MTBF / ( MTBF ＋ MTTR )  
つまり  
稼働率 ＝ 動作した時間 / 全体の時間  
```

- 直立・並列の話  
  稼働率が0.9のサーバを直列・並列で2台つないだ時の稼働率  
  - 直立の場合  
    0.9 * 0.9 = 0.81  
  - 並列の場合  
    1 - (1-0.9²) = 0.99  

- リージョンとAZ  
  リージョンは地域ごとの区切り。AZはリージョン内のデータセンタ区切り  
  →マルチリージョンは災害対策など  
 

### 移行関連のAWSサービス  

押さえておきたいAWS移行サービス全12種類  
AWSには多くの移行関連ツールがあります。以下は、AWSの移行に必要な12のツールの解説です¹:  

1. **AWS Migration Hub**:  
  複数の AWS およびパートナーソリューション間でのアプリケーション移行の進行状況を追跡できます。  
2. **AWS Application Discovery Service**:  
  オンプレミスのデータセンターに関する情報を収集することで、移行プロジェクトを計画するのに役立ちます。  
3. **Migration Evaluator**:  
  AWS への移行に関する意思決定を無料で加速できます。  
4. **AWS Server Migration Service**:  
  オンプレミスの VMware vSphere、マイクロソフトの Hyper-V/SCVMM、および Azure 仮想マシンの AWS クラウドへの移行を自動化します。  
5. **CloudEndure Migration**:  
  物理ベース、仮想、またはクラウドベースのインフラストラクチャから AWS にアプリケーションを無償で移行するための CloudEndure Migrationを提供しています。  
6. **AWS Database Migration Service**:  
  データベースの移行を簡素化します。  
7. **AWS Schema Conversion Tool**:   
  データベーススキーマの変換を自動化します。  
8. **AWS Snowball**:  
  大量のデータをオフラインで AWS に移行するための物理デバイスです。  
9. **AWS Snowball Edge**:  
  データセンターから AWS にデータを移行するための物理デバイスです。  
10. **AWS Snowmobile**:  
  データセンターから AWS にペタバイト単位のデータを移行するための物理デバイスです。  
11. **AWS Transfer for SFTP**:  
  SFTP クライアントを使用してファイルを AWS に移行するためのサービスです。  
12. **AWS DataSync**:  
  オンプレミスのストレージと AWS ストレージ間でデータを移行するためのサービスです。  

以上が、AWSの移行に必要な12のツールの解説です¹。ご参考になれば幸いです。

ソース: Bing との会話 2024/1/8
(1) [これだけは押さえておきたい、AWS移行全12ツール一挙紹介](https://aws.amazon.com/jp/blogs/psa/migration_tools/)  
(2) [オンプレミスサーバーのAWS移行で活躍する様々なツール](https://www.stylez.co.jp/columns/various_tools_for_migrating_to_aws/)  
(3) [クラウド「AWS」への移行のポイントは？特徴と移行メリットを](https://www.sunnycloud.jp/column/20201204-01/)  
(4) [クラウド移行の最初の一歩 ～ AWSで使える移行ツール](https://managed.gmocloud.com/knowledge/aws/migration04.html)  
(5) [AWS での移行および転送サービス | Amazon Web Services] (https://aws.amazon.com/jp/products/migration-and-transfer/)  


### 認証系サービス  

- AWS Organizations  
  AWSアカウントの統合管理  
  「AWSアカウント」は個人個人のアカウントではなく、環境ごとのアカウントという意味 
  個人個人のアカウントはIAMが管理   
- Amazon Cognito  
  アプリケーションの認証システム  




