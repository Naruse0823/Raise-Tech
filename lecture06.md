# 第6回課題
## AWS を利用した日の記録をCloudTrail のイベントから探し出す（イベント名とその内容を3つピックアップ）
- イベント名  
ConsoleLogin→ユーザー認証  
- 内容  
"eventTime": "2024-07-07T04:01:38Z"→2024年7月7日04時01分38秒（UTC）  
"eventSource": "signin.amazonaws.com"→AWSアカウントにログイン  
"awsRegion": "ap-northeast-1"→東京リージョン  
![CloudTrail1](images/lecture06-1(1).png)
![CloudTrail2](images/lecture06-1(2).png)
## CloudWatch アラームを使って、ALB のアラームを設定し、メール通知
- アラーム状態の場合
![アラーム状態](images/lecture06-2(1).png)
![アラームの通知](images/lecture06-2(2).png)
- OK状態の場合
![OK状態](images/lecture06-3(1).png)
![アラーム解除通知](images/lecture06-3(2).png)
## 今日までに作成したリソースの利用料の見積もりを作成（URLで共有）
- 第5回課題で作成した構成と稼働状況を元に見積もりを作成  
[見積もりの共有URL](https://calculator.aws/#/estimate?id=369aca1d14d1b039da2d8314bc2f18d913a653a2)
## 現在の利用料の確認(先月のEC2の利用状況から)
- 6月の合計
![6月の合計](images/lecture06-4(1).png)
- サービス別料金表
![6月のサービス別](images/lecture06-4(2).png)
### 学んだことや感想など
- 無料枠が無かったらという見積もりを作成して驚いた。いまは無料枠が適応されているので、そこまでかかっていないが、より一層リソースを管理して、無駄な利用料金がかからないように注意していく。また、Cost Explorer、Budgetなども利用して、予算超過も防ぎたい。
- ターミナル上で見ていたエラーログとはまた違ったログだった。様々な種類のログが存在していることが分かったので、現場に出たときに信用を失わないないためにも、今のうちに見慣れておく必要があると感じた。