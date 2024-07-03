# 第5回課題
## 組み込みサーバー（puma）のみ
![only-puma](images/lecture05-1.png)
## UNIXsocketに変更し、curlを使って動作確認
![UNIXsocket](images/lecture05-2(1).png)
![curl](images/lecture05-2(2).png)
## Nginxの単体起動確認
![Nginx](images/lecture05-3.png)
## puma,nginx,UNIXsocketで起動確認
![puma,nginx,UNIXsocket](images/lecture05-4.png)
## ALBを追加して起動確認
![ALB作成](images/lecture05-5(1).png)
![target](images/lecture05-5(2).png)
![接続](images/lecture05-5(3).png)
## railsアプリの画像の保存先をS3に変更
![S3バケット作成](images/lecture05-6(1).png)
![IAMロール](images/lecture05-6(2).png)
![ポリシー](images/lecture05-6(3).png)
![EC2に付与](images/lecture05-6(4).png)
![バケットポリシー](images/lecture05-6(5).png)
![接続確認](images/lecture05-6(6).png)
![保存確認](images/lecture05-6(7).png)
![小](images/lecture05-6(8).png)
![中](images/lecture05-6(9).png)
![大](images/lecture05-6(10).png)
## AWS構成図
![AWS構成図](images/lecture05-7.png)
### 感想
- 提出までにものすごい時間をかけてしまった。何度も何度も嫌になったが、なんとかやりきった。遅れてしまった分をなるべく取り戻したい！！
- CSSの反映、railsアプリ7以上のときの画像表示、親ディレクトリのパーミッションを変更しないと子のディレクトリのパーミッションをいくら変更しても権限が適応されない？については一生忘れない。