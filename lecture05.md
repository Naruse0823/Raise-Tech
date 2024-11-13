# 第5回課題<!-- omit in toc -->

## 目次<!-- omit in toc -->
- [組み込みサーバー(puma)のみで起動確認](#組み込みサーバーpumaのみで起動確認)
- [UNIXsocketに変更しcurlを使って起動確認](#unixsocketに変更しcurlを使って起動確認)
- [Nginxの単体起動確認](#nginxの単体起動確認)
- [UNIXsocketを用いてのpumaとnginxの接続確認](#unixsocketを用いてのpumaとnginxの接続確認)
- [ALBを追加して起動確認](#albを追加して起動確認)
- [railsアプリの画像の保存先をS3に変更](#railsアプリの画像の保存先をs3に変更)
- [AWS構成図](#aws構成図)
- [感想](#感想)

## 組み込みサーバー(puma)のみで起動確認
ここまでの手順は[こちら](lecture05/1-pumaのみ.md)に記載しております。
- 組み込みサーバーのみで起動確認
![only-puma](images/lecture05-1.png)

## UNIXsocketに変更しcurlを使って起動確認
ここまでの手順は[こちら](lecture05/2-UNIXsocket.md)に記載しております。
- UNIXsocketのみでpuma起動
![UNIXsocket](images/lecture05-2(1).png)
- curlで確認
![curl](images/lecture05-2(2).png)

## Nginxの単体起動確認
ここまでの手順は[こちら](lecture05/3-Nginx単体.md)に記載しております。
- nginxのサーバーの起動確認とブラウザ確認
![Nginx](images/lecture05-3.png)

## UNIXsocketを用いてのpumaとnginxの接続確認
ここまでの手順は[こちら](lecture05/4-pumaとnginx.md)に記載しております。
- UNIXsocketを用いてのpumaとnginxの接続確認
![pumaとnginx](images/lecture05-4.png)

## ALBを追加して起動確認
ここまでの手順は[こちら](lecture05/5-ALB.md)に記載しております。
- ALB作成
![ALB作成](images/lecture05-5(1).png)
- ヘルスチェック
![target](images/lecture05-5(2).png)
- DNSで起動確認
![接続](images/lecture05-5(3).png)

## railsアプリの画像の保存先をS3に変更
ここまでの手順は[こちら](lecture05/6-画像の保存先をS3に変更.md)に記載しております。
- S3バケット作成
![S3バケット作成](images/lecture05-6(1).png)
- IAMロール作成
![IAMロール](images/lecture05-6(2).png)
- ポリシー作成
![IAMのポリシー](images/lecture05-6(3).png)
- EC2にIAMロールを付与
![EC2に付与](images/lecture05-6(4).png)
- 起動確認
![接続確認](images/lecture05-6(6).png)
- railsアプリの画像保存先をS3に変更
![保存確認](images/lecture05-6(7).png)
- 保存された画像
![大](images/lecture05-6(10).png)
![中](images/lecture05-6(9).png)
![小](images/lecture05-6(8).png)
## AWS構成図
- 今回の構成
![AWS構成図](images/lecture05-7.png)

## 感想
- 提出までにものすごい時間をかけてしまった。何度も何度も嫌になったが、なんとかやりきった。遅れてしまった分をなるべく取り戻したい！！
- CSSの反映、railsアプリ7以上のときの画像表示の仕方、親ディレクトリに適切な権限がないと、その中の子ディレクトリやファイルにアクセスすることができないことについては一生忘れない。