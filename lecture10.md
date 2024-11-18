# 第10回課題
## 目次<!-- omit in toc -->
[1. 作成したテンプレートファイル](#1-作成したテンプレートファイル)<br>[2. 作成手順](#2-作成手順)<br>[3. VPC](#3-vpc)<br>[4. EC2](#4-ec2)<br>[5. ALB](#5-alb)<br>[6. RDS](#6-rds)<br>[7. S3](#7-s3)<br>[8. 接続確認](#8-接続確認)<br>[9. 感想](#9-感想)

### 1. 作成したテンプレートファイル
- [CF-VPC.yml](CF-lecture10/CF-VPC.yml)
- [CF-EC2.yml](CF-lecture10/CF-EC2.yml)
- [CF-ELB.yml](CF-lecture10/CF-ELB.yml)
- [CF-RDS.yml](CF-lecture10/CF-RDS.yml)
- [CF-S3.yml](CF-lecture10/CF-S3.yml)

**【内訳】**
|テンプレート|リソース内訳|
|:--|:--|
|CF-VPC.yml|・VPC<br>・PublicSubnet(a,c)<br>・PrivateSubnet(a,c)<br>・PublicRouteTable<br>・PrivateRouteTable(a,c)<br>・InternetGateway<br>・InternetGatewayAttachment<br>・PublicRoute<br>・PublicSubnet(a,c)RouteTableAssociation<br>・PrivateSubnet(a,c)RouteTableAssociation<br>|
|CF-EC2.yml|・EC2SecurityGroup<br>・EC2<br>・ InstanceProfile<br>|
|CF-ELB.yml|・TargetGroup<br>・ALB<br>・ALBListener<br>・ALBSecurityGroup<br>|
|CF-RDS.yml|・RDSSubnetGroup<br>・RDSInstance<br>・RDSSecurityGroup<br>|
|CF-S3.yml|・S3Bucket<br>|

<br>

### 2. 作成手順
- 「cloudformation」と検索し、「cloudformation」をクリック

![1-検索](./images/lecture10-9.png)
- 「スタックの作成」または「スタックの作成→新しいリソースを使用」をクリック

![2-スタックの作成](./images/lecture10-10.png)
- テンプレートの準備は「既存のテンプレートを選択」を選択
- テンプレートソースは「テンプレートファイルのアップロード」を選択し、作成したファイルをアップロードしたら、「次へ」をクリック

![3-アップロード](./images/lecture10-11.png)
- 「スタック名」を入力
- 「パラメータ」をファイル内で設定した場合は、必要事項を設定し「次へ」をクリック

![4-スタック名・パラメータ](./images/lecture10-12.png)
- 「任意のタグ」や「任意のアクセス許可」を設定

![5-タグ・アクセス許可](./images/lecture10-13.png)
- プロビジョニング失敗時の動作は「すべてのスタックリソースをロールバックする」を選択
- ロールバック中に新しく作成されたリソースを削除するについては「削除ポリシーを使用する」を選択

![6-スタックの失敗オプション](./images/lecture10-14.png)
- 「詳細オプション」は必要があれば設定する
- テンプレートファイルを用いてIAMリソースを作成する場合は、チェックボックスに「チェック」を入れ、「次へ」をクリック

![7-詳細オプション・IAM確認](./images/lecture10-15.png)
- 最終確認をして、問題なければ「送信」をクリック
- 画像のような状態になれば、作成完了

![8-作成完了画面](./images/lecture10-16.png)
<br>

### 3. VPC
- VPC  

![VPC](images/lecture10-1.png)
 <br>
 
### 4. EC2
- EC2  

![EC2](images/lecture10-2.png)
![EC2(2)](images/lecture10-2(2).png)
- EC2 sg

![EC2 sg](images/lecture10-2(3).png)
<br>

### 5. ALB
- ALB  

![ALB](images/lecture10-3.png)

- target group  

![target group](images/lecture10-4.png)
<br>

### 6. RDS
- RDS  

![RDS](images/lecture10-5.png)
- RDS sg

![RDS sg](images/lecture10-5(2).png)
<br>

### 7. S3
- S3  

![S3](images/lecture10-6.png)
<br>
  
### 8. 接続確認
- EC2  

![接続確認　EC2](images/lecture10-7.png)
- RDS  

![接続確認　RDS](images/lecture10-8.png)
<br>
  
### 9. 感想
- 記述しなくてもデフォルトで自分の思っている設定がされるものがあるので、そこは書かずになるべくすっきりとさせた。その際、少しだが公式ドキュメントになれることが出来たと思う。
- すべて書き終わって思ったのは、1つにまとめた方が書きやすいと思った。しかし、今回は初めてということもあり、まとめて書くとぐちゃぐちゃになりそうだと思ったので、サービスごとに分けてみた。開発の仕方によって、そのときの適切な方法が異なると思うので、どちらにもなれておきたい。