# RaiseTech AWSコース 課題実践ポートフォリオ

このリポジトリは、RaiseTech AWSコースで学習した内容と、各課題の実践記録です。国税専門官からクラウドエンジニアへのキャリアチェンジを目指し、日々スキル習得に取り組んでいます。

---

## 最終成果物（課題１３）  
  
* 成果物  
[サンプルアプリケーション](https://github.com/yuta-ushijima/raisetech-live8-sample-app.git)の自動デプロイ  
  
* 仕組み  
Circleciで以下項目を完全自動化デプロイ  
  * 簡易フロー  
    * cfn-lintでCloudFormationの構文チェック  
    * CloudformationでAWS環境構築  
    * AnsibleでRailsアプリケーションの構成管理  
    * Serverspecで自動テスト  
  * 具体的フロー  
    GitHubにプッシュされると、CircleCIのワークフローが自動的に開始されます。まず、`cfn-lint`でCloudFormationテンプレートの構文をチェックし、問題がなければCloudFormationスタックを作成してAWSインフラを構築します。次にAnsibleを実行して、EC2インスタンス上にRuby on Railsの実行環境をセットアップし、アプリケーションをデプロイします。最後にServerspecでサーバーの状態が期待通りであることをテストし、デプロイの正当性を保証します。  
  
* 構成図  
  * ![構成図](img2/lecture14.drawio.png)  

---

## 達成課題と習得技術

これまでに以下の学習に取り組み、クラウドエンジニアリングの基礎からCI/CD構築までを実践的に学習しました。  
  
| 課題 | 学習内容 | 学習技術 | ファイル |
| :----: | :------------ | :------------ | :----------: |
| **1**  | **AWSアカウント作成**<br>AWSアカウントの作成。ルートユーザーとIAMユーザーのMFA設定。 | IAM, MFA | - |
| **2**  | **GitとGitHubの基礎**<br>GitとGitHubの設定。GitHubリポジトリの作成。ブランチの作成とプルリクエストの発行。Markdown記法での成果報告。 | Git, GitHub, Markdown | [lecture02.md](lecture02.md) |
| **3**  | **サンプルアプリケーションのデプロイ**<br>EC2とRDSを使用してRailsアプリケーションのデプロイを経験。APサーバーとDBサーバーの学習。bundlerの学習。 | EC2, RDS, bundler | [lecture03.md](lecture03.md) |
| **4**  | **AWSリソースの構築とEC2にSSH接続**<br>AWSのVPC、サブネット、ルーティングを設定し、セキュアなネットワーク環境を構築。EC2とRDSのセキュリティグループ設定と接続確認を実施。 | VPC, Subnet, セキュリティグループ, SSH | [lecture04.md](lecture04.md) |
| **5**  | **サンプルアプリケーションのデプロイ**<br>EC2上にRails環境を構築し、Nginxをリバースプロキシとして導入。Unix Socketを介したPumaとNginxの連携、ALBによる負荷分散、S3による静的ファイルホスティングを実装。 | EC2, RDS, Ruby, Rails, Puma, Nginx, Unix Socket, ALB, S3, IAM, 構成図 | [lecture05.md](lecture05.md) |
| **6**  | **CloudTrail、CloudWatchの利用、AWS利用料の見積**<br> CloudTrailでAWS APIアクティビティを監視。CloudWatchでALBのヘルスチェックに基づいたアラームを設定。AWS Cost Explorerで利用費を分析し、最適化の学習。 | CloudWatch, CloudTrail, ALB, AWS, Cost Explorer | [lecture06.md](lecture06.md) |
| **7**  | **AWSでのセキュリティ対策**<br>作成した環境がどのような攻撃に対して脆弱かの検討 | SQLインジェクションやXSS、DDoS攻撃、不正なSSHアクセスといった脅威に対し、WAFの導入やセキュリティグループとIAMの最小権限の原則の徹底、踏み台サーバーの設置や監査ログの取得などの対策が上げられる | - |
| **8**  | **サンプルアプリケーションのデプロイ(実演)**<br>Railsアプリケーションのデプロイ構築の実演 | - | - |
| **9**  | **サンプルアプリケーションのデプロイ（実演）**<br>Railsアプリケーションのデプロイ構築の実演 | - | - |
| **10** | **CloudFormationによるIaC実践**<br>これまでの手動構築をCloudFormationテンプレートでコード化し、インフラの自動デプロイを実現。 | CloudFormation, VPC, Subnet, EC2, RDS, ALB, S3, セキュリティグループ | [lecture10.md](lecture10.md) |
| **11** | **Serverspecによるインフラテスト自動化**<br>CloudFormationで構築した環境に対し、Serverspecフレームワークを用いてサーバー構成の自動テストを導入。インフラの品質保証を自動化。 | Serverspec, Rspec, Ruby | [lecture11.md](lecture11.md) |
| **12** | **CircleCIを用いたCI/CDパイプライン構築 (基礎)**<br>CircleCIを導入し、CI/CDパイプラインの基礎を構築。CloudFormationのハードコーディングやパスワード管理の問題をParametersとSecrets Managerで解決。 | CircleCI, CloudFormation , AWS Secrets Manager | [lecture12.md](lecture12.md) |
| **13** | **CircleCIによるCI/CDパイプライン完成**<br>`cfn-lint`、`execute-cloudformation`、`execute-ansible`、`execute-serverspec`を統合した完全なCI/CDパイプラインを構築。インフラからアプリケーションデプロイ、テストまでの一連のプロセスを自動化。 | CircleCI, cfn-lint, CloudFormation, Ansible, Serverspec | [lecture13.md](lecture13.md) |
| **14** | **自動化構築の構成図の作成とリポジトリのREADME作成**<br>CI/CDパイプラインで構築した自動化の構成図を作成しリポジトリのREADME作成 | - | [lecture14.md](lecture14.md) |
| **15** | **CircleCIによるCI/CDパイプライン完成(実演)**<br>CI/CDパイプラインの構築の実演 | - | - |
| **16** | **現場で求められる実践的スキルの習得**<br>AWS自動化の知識に加え、現場で活躍するために必要な応用スキルと、今後の学習指針を明確化 | 学習指針:インフラ設計、運用監視、コンテナ技術、チーム開発、可視化・検証 | - |