# AWS クラウドプラクティショナー  

## 用語集  

__ECS__  
Elastic Container Service  
Dockerコンテナを簡単に実行、停止、管理するサービス  

__CloudWatch__  
AWSアプリケーションの監視。EC2のCPU利用率とかも見る。  
サービス知しては3つ  
- Cloudwatch  
- Cloud watch log  
- Cloud Event  

__CloudTrail__
アクセス監視サービス。APIの利用なども監視できる。  
ユーザーのアクティビティログを取得することができる監視サービス  

__AWS config__  
構成管理に使用されるサービス  

__System Manager__
フリートマネージャー使ってたサービス  

__ネットワークACL__  
ネットワークAccess Control List  
サブネット単位での通信制御  

__AWS Migration hub__  
AWSへの大規模移行する際に色々ツールを使うが、それらを管理するサービスのこと  

__AWS Application Discovery Service__  
オンプレの情報を収集して、データ移行計画を立案するサービス  

__AWS Application Migration Service__  
昔はServer Migration Serviceと言っていた。  
サーバーやオンプレのインフレ、Azureからの移行をするサービス。  

__AWS Databased Migration Service__  
データベースの移行をするサービス  
※Migration…日本語で「移動」の意味  

__EBS__  
Elastic Block Store  
EC2がディスクとして利用しているサービス  

__ElastiCathe__  
NoSQLデータをメモリ上にキャッシュとして格納することで高速化を測るDBサービス  

__SES__  
Simple Email Service  
メールサービスのこと  
__SMS__  
Server Magration Service  
さっき書いた
__SNS__  
Simple Notification Service  
Notification…通知  
様々なアプリケーションに通知を行う(push方式)  
__SQS__  
Simple Queue Service  
重たい処理とかをキューイング処理してくれる。並列処置が可能(ポーリング処理)  

__CloudFront__  
動画を世界中に配信したいときに使えるサービス  

__Amazon Elastic Transcoder__  
S3に保管した動画ファイルを再生アプリに応じて形式変換してくれるサービス  

__Amazon Interactive Video Service__  
動画配信のなんちゃらかんちゃら  


## 文章問題  
EC2の通信を制御するために使用する機能  
  →セキュリティグループ    
ネットワークACLとの違いは、サブネットを制御するか、EC2単体を制御するかの違い（EC2単体がセキュリティグループ）  

__マルチAZ展開とマルチリージョン展開__  
稼働率の担保はAZ展開  
ホットスタンバイなどの災害対応はリージョン展開  

## EC2の課金種類  
[参考](https://www.awsjp.com/AWS/hikaku/OndemandInstance-ReservedInstance-SpotInstance-hikaku.html)  

- オンデマンドインスタンス  
　使うだけお金がかかる  
  →Dedicated host  
    物理的に占有したいときに使用  
- リザードブルインスタンス  
  1年or3年契約で利用する  
- スケジュールドリザーブルドインスタンス（2021年に利用停止）  
  定期的に使うときに利用する（毎週金曜日とか）  




