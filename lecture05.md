# 第5回課題
## 組み込みサーバー（puma）のみ
- 組み込みサーバーのみで起動確認
![only-puma](images/lecture05-1.png)
## UNIXsocketに変更し、curlを使って動作確認
- UNIXsocketのみでpuma起動
![UNIXsocket](images/lecture05-2(1).png)
- curlで確認
![curl](images/lecture05-2(2).png)
## Nginxの単体起動確認
- nginxのサーバーの起動確認とブラウザ確認
![Nginx](images/lecture05-3.png)
## puma,nginx,UNIXsocketで起動確認
- pumaとnginxをUNIXsocketで起動確認
![puma,nginx,UNIXsocket](images/lecture05-4.png)
## ALBを追加して起動確認
- ALB作成
![ALB作成](images/lecture05-5(1).png)
- ヘルスチェック
![target](images/lecture05-5(2).png)
- DNSで起動確認
![接続](images/lecture05-5(3).png)
## railsアプリの画像の保存先をS3に変更
- S3バケット作成
![S3バケット作成](images/lecture05-6(1).png)
- IAMロール作成
![IAMロール](images/lecture05-6(2).png)
- ポリシー作成
![IAMのポリシー](images/lecture05-6(3).png)
- EC2にIAMロール付与
![EC2に付与](images/lecture05-6(4).png)
- 起動確認
![接続確認](images/lecture05-6(6).png)
- railsアプリの画像保存先をS3に変更
![保存確認](images/lecture05-6(7).png)
- 保存された画像
![小](images/lecture05-6(8).png)
![中](images/lecture05-6(9).png)
![大](images/lecture05-6(10).png)
## AWS構成図
- 今回の構成
![AWS構成図](images/lecture05-7.png)
### 感想
- 提出までにものすごい時間をかけてしまった。何度も何度も嫌になったが、なんとかやりきった。遅れてしまった分をなるべく取り戻したい！！
- CSSの反映、railsアプリ7以上のときの画像表示、親ディレクトリのパーミッションを変更しないと子のディレクトリのパーミッションをいくら変更しても権限が適応されないことについては一生忘れない。