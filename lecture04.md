# 第４回課題  
## VPC  
![VPC①](img01/lecture04-3.png)  
![VPC②](img01/lecture04-4.png)   
  
## サブネット  
+ ap-northeast-1c パブリックサブネット  
![サブネット①](img01/lecture04-5.png)  
+ ap-northeast-1c プライベートサブネット  
![サブネット②](img01/lecture04-6.png)  
+ ap-northeast-1a パブリックサブネット  
![サブネット③](img01/lecture04-7.png)  
+ ap-northeast-1a プライベートサブネット  
![サブネット④](img01/lecture04-8.png)  

## EC2  
![EC2](img01/lecture04-11.png)  

## RDB  
![RDB①](img01/lecture04-9.png)  
![RDB②](img01/lecture04-10.png)  

## セキュリティグループ  
+ EC2インバウンド  
![EC2in](img01/lecture04-12.png)  
+ EC2アウトバウンド  
![EC2out](img01/lecture04-13.png)  
+ RDSインバウンド  
![RDSin](img01/lecture04-14.png)  
+ RDSアウトバウンド  
![RDSout](img01/lecture04-15.png)  

## EC2にSSH接続  
![SSH接続](img01/lecture04-1.png)  

## EC2とRDSの接続  
![接続確認](img01/lecture04-2.png)  

## 所感  
初めてVPCとサブネットを作成した際は、IPv4 CIDRの設定値に関して、サブネットが作成不可というエラーが繰り返し起き大変であった。これはCIDRの意味とサブネットの意味を理解しきれていないことが原因であった。
しかし、今回は作成が複数回目ということもあり、以前よりCIDRの理解も進んでおり、難なくサブネットを作成することに成功し、微小であるが進歩を感じた。