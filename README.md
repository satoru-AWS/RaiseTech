# RaiseTech AWSコース 課題実践ポートフォリオ

このリポジトリは、RaiseTech AWSコースで学習した内容と、各課題の実践記録です。国税専門官からクラウドエンジニアへのキャリアチェンジを目指し、日々スキル習得に取り組んでいます。

---

## 達成課題と習得技術

これまでに以下の課題に取り組み、クラウドエンジニアリングの基礎からCI/CD構築までを実践的に学習しました。

| 課題番号 | 課題内容の概要 | 主な習得技術 |
| :------- | :------------- | :----------- |
| **課題2** | **GitとGitHubの基礎**<br>バージョン管理システムの理解とGit/GitHubの基本操作を習得。チーム開発におけるGit-Flow、GitHub-Flowを学習。 | Git, GitHub, Markdown |
| **課題3** | **EC2とRDSによるアプリケーションデプロイ**<br>EC2とRDS（MySQL）を利用したRuby on Railsサンプルアプリケーションのデプロイを経験。Bundlerを学習。 | AWS EC2, AWS RDS (MySQL), Ruby on Rails, Puma, MySQL, Bundler |
| **課題4** | **AWSネットワーク（VPC）とセキュリティグループ構築**<br>AWSのVPC、サブネット、ルーティングを設定し、セキュアなネットワーク環境を構築。EC2とRDSのセキュリティグループ設定と接続確認を実施。 | AWS VPC, AWS Subnet, Security Group, SSH |
| **課題5** | **Nginx/ALB/S3連携によるWebアプリケーション強化**<br>EC2上にRails環境を構築し、Nginxをリバースプロキシとして導入。Unix Socketを介したPumaとNginxの連携、ALBによる負荷分散、S3による静的ファイルホスティングを実装。 | AWS EC2, AWS RDS, Ruby, Rails, Puma, Nginx, Unix Socket, AWS ALB, AWS S3, IAM, Active Storage |
| **課題6** | **CloudTrailとCloudWatchによる監視・コスト分析**<br>CloudTrailでAWS APIアクティビティを監視。CloudWatchでALBのヘルスチェックに基づいたアラームを設定。AWS Cost Explorerで利用費を分析し、最適化の視点を学習。 | AWS CloudTrail, AWS CloudWatch, AWS ALB, AWS Cost Explorer |
| **課題10** | **CloudFormationによるIaC実践**<br>これまでの手動構築をCloudFormationテンプレートでコード化し、インフラの自動デプロイを実現。 | AWS CloudFormation, AWS VPC, AWS Subnet, AWS EC2, AWS RDS, AWS ALB, AWS S3, Security Group |
| **課題11** | **Serverspecによるインフラテスト自動化**<br>CloudFormationで構築した環境に対し、Serverspecフレームワークを用いてサーバー構成の自動テストを導入。インフラの品質保証を自動化。 | Serverspec, Rspec, Ruby |
| **課題12** | **CircleCIを用いたCI/CDパイプライン構築 (基礎)**<br>CircleCIを導入し、CI/CDパイプラインの基礎を構築。CloudFormationのハードコーディングやパスワード管理の問題をParametersとSecrets Managerで解決。 | CircleCI, AWS CloudFormation (Parameters), AWS Secrets Manager |
| **課題13** | **CircleCIによるCI/CDパイプライン完成**<br>`cfn-lint`、`execute-cloudformation`、`execute-ansible`、`execute-serverspec`を統合した完全なCI/CDパイプラインを構築。インフラからアプリケーションデプロイ、テストまでの一連のプロセスを自動化。 | CircleCI, cfn-lint, AWS CloudFormation, Ansible, Serverspec |

---

## 課題13の構成図

課題13では、以下のCI/CDパイプラインを構築し、インフラからアプリケーションデプロイ、テストまでを自動化しました。

```mermaid
graph TD
    A[コード変更をPush] --> B(GitHub)
    B --> C{CircleCI}
    C -- 1. cfn-lint --> D[CloudFormation構文チェック]
    D -- 2. execute-cloudformation --> E[AWS環境構築]
    E -- 3. execute-ansible --> F[Railsアプリ環境構築]
    F -- 4. execute-serverspec --> G[自動テスト]
    G -- 成功 --> H[ALB経由でアクセス可能]
    G -- 失敗 --> I[エラー通知]