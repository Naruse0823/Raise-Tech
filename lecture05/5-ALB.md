# 5.ALBを追加して起動確認

### ① targetグループ作成とヘルスチェック
<br>

**ターゲットグループ作成**
- EC2のサイドバーから「ターゲットグループ」をクリック
- 「ターゲットグループの作成」をクリック

![1-ターゲットグループの作成](./lecture05-images/readme-lecture05-5-1.png)
- 「インスタンス」を選択

![2-作成画面1](./lecture05-images/readme-lecture05-5-2.png)
- 任意のターゲットグループ名を入力
- プロトコル：ポートは「HTTP 80」
- IPアドレスタイプは「IPv4」
- VPCは「使用しているEC2が含まれるVPC」を選択
- プロトコルバージョンは「HTTP1」
- 「次へ」をクリック

![3-名前～プロトコルバージョン](./lecture05-images/readme-lecture05-5-3.png)
<br>

**ターゲットを登録**
- 「保留中として以下を含める」を選択し、「ターゲットグループの作成」をクリック

![4-ターゲットを登録](./lecture05-images/readme-lecture05-5-4.png)
<br>

### ②ALB用にセキュリティグループ作成
- インバウンドは「ポート80を開放してソースを0.0.0.0/0」に、アウトバウンドは「すべてのポートを開放し送信先を0.0.0.0/0」に設定

![5-ALBインバウンド](./lecture05-images/readme-lecture05-5-5.png)
![6-ALBアウトバウンド](./lecture05-images/readme-lecture05-5-6.png)
<br>

### ③ ロードバランサーを作成し、ヘルスチェック
<br>

**ロードバランサーの作成**
- EC2のダッシュボードまたはサイドバーから「ロードバランサー」をクリック
- 「ロードバランサーの作成」をクリック
- 「Application Load Balancer」を選択

![7-ALB選択](./lecture05-images/readme-lecture05-5-7.png)
- 「任意のロードバランサー名」を入力
- スキームは「インターネット向け」
- ロードバランサーのIPアドレスタイプは「IPv4」

![8-名前～IPアドレスタイプ](./lecture05-images/readme-lecture05-5-8.png)
- VPCは「使用しているEC2が含まれているもの」を選択
- マッピングのサブネットは最低2つ選択する必要があるため、1つは「使用しているEC2が含まれるサブネット」、もう1つは「別のパブリックサブネット」を選択

![9-マッピング](./lecture05-images/readme-lecture05-5-9.png)
- セキュリティグループは「先ほど作成したセキュリティグループ」を選択
- リスナーとルーティングは転送先に「先ほど作成したターゲットグループ」を選択

![10-セキュリティグループ・リスナーとルーティング](./lecture05-images/readme-lecture05-5-10.png)

![11-確認](./lecture05-images/readme-lecture05-5-11.png)
![作成完了画面](../images/lecture05-5(1).png)
<br>

**ヘルスチェック**
- nginxサーバーを起動させておかないと「異常」となってしまうので、起動させておく

![ヘルスチェック](../images/lecture05-5(2).png)
<br>

### ④ アドレスバーにロードバランサーのDNS名を入力して、接続確認するとエラー

![12-DNS名を入力して開くとエラー](./lecture05-images/readme-lecture05-5-12.png)
↓
- development.rb に「config.hosts << "ALBのDNS名"」を追記し、再起動

![13-development.rb](./lecture05-images/readme-lecture05-5-13.png)
```sh
sudo systemctl restart puma
```
<br>

### ⑤再度DNS名をブラウザのアドレスバーに貼り付けて接続確認

![DNS名で接続確認](../images/lecture05-5(3).png)
<br>

### ⑥セキュリティを高めるため、EC2のセキュリティグループのインバウンドで、ポート80のソースを「使用しているEC2を含むVPCのIPアドレス」に変更し、再度接続確認