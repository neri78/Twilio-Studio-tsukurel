#  手順1: 新しいコールフローの作成

この手順では、Twilio Studioを用いて新しいフローを作成する方法を学びます。

## 前提条件
Twilioアカウントが必要になります。事前に案内されたリンク、または下記の記事を参考にアカウントを作成してください。  
[Twilioアカウントの作成方法](https://www.twilio.com/blog/how-to-create-twilio-account-jp)

## 1-1. Studioフローの新規作成

[Twilioコンソール](https://jp.twilio.com/console)にサインインし、画面左のナビゲーションから[Studio](https://jp.twilio.com/console/studio)を選択します。

![コンソール](../assets/01-Console.png)

[Studioダッシュボード](https://jp.twilio.com/console/studio/dashboard)が表示されます。初めてフローを作成する場合は`Create a flow`ボタンをクリックします。以前に作成したことがある場合は既存のフロー一覧が表示されている状態で`+`ボタンをクリックします。

- 初めてフローを作成する場合  
![初めてフローを作成する場合](../assets/01-Create-First-Flow.png)

- 既存のフローが存在する場合  
![既存フローが存在する場合](../assets/01-Existing-Flows.png)


フローの名前を設定します。わかりやすい名前をつけ、`Next`ボタンをクリックします。

![フローの名前を設定](../assets/01-Flow-Name.png)

いくつかテンプレートが表示されますが、このハンズオンではフルスクラッチで作成するため`Start from scratch`を選択し、`Next`ボタンをクリックします。

![まっさらな状態で開始](../assets/01-Flow-Template.png)

初期化が完了するとデザイン画面が表示されます。デザイン画面には大きく分けて3つの領域が用意されています。

![デザイン画面](../assets/01-Design-Screen.png)

|領域の番号 |説明 |
|:-------:|:--------|
|1|デザインキャンバスの操作およびフローの公開を制御|
|2|デザインキャンバス、ここにウィジェットを配置する |
|3|ウィジェットライブラリ、アクションやフロー制御を行う __部品__ が準備されている |

これらを利用しフローを作成します。
今回はここまでとなりますが、各ウィジェットの説明を下記で確認できます。

-------------------------------------

### 各ウィジェットの概要

|イメージ|ウィジェットの名前 |種類 |説明 |
|:-------:|:-------:|:--------|:--------|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/trigger.width-500.png" />|[Trigger](https://jp.twilio.com/docs/studio/widget-library/trigger-start)|Flow Control|フローの開始となるウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/splitbasedon.width-500.png" />|[Split Based On...](https://jp.twilio.com/docs/studio/widget-library/split-based-on)|Flow Control|フローの分岐を指定できるウィジェット |
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/Screen_Shot_2018-11-29_at_9.15.43_AM.width-500.png" />|[Set Variables](https://jp.twilio.com/docs/studio/widget-library/set-variables)|Flow Control|フロー内で入力された内容を保持できる変数を設定できるウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/gatherinputoncall.width-500.png" />|[Gather Input On Call](https://jp.twilio.com/docs/studio/widget-library/gather-input-call)|VOICE|ユーザーからの入力を受け取るウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/connectcallto.width-500.png" />|[Connect Call To](https://jp.twilio.com/docs/studio/widget-library/connect-call)|VOICE|通話を別の番号、ユーザーに転送するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/Make_Outgoing_Call.width-500.png" />|[Make Outgoing Call](https://jp.twilio.com/docs/studio/widget-library/make-outgoing-call)|VOICE|外部発信を行うウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/recordvoicemail.width-500.png" />|[Record Voicemail](https://jp.twilio.com/docs/studio/widget-library/record-voicemail)|VOICE|ボイスメールの録音を行うウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/Screen_Shot_2019-07-10_at_11.19.12_PM.width-500.png" />|[Call Recording](https://jp.twilio.com/docs/studio/widget-library/call-recording)|VOICE|通話録音を開始または終了するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/enqueue-widget.width-500.png" />|[Enqueue Call](https://jp.twilio.com/docs/studio/widget-library/enqueue-call)|VOICE|現在の通話をコールキューに挿入するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/sayplay.width-500.png" />|[Say/Play](https://jp.twilio.com/docs/studio/widget-library/sayplay)|VOICE|テキストまたは音声ファイルを再生するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/fork_stream_widget.width-500.png" />|[Fork Stream](https://jp.twilio.com/docs/studio/widget-library/fork-stream)|VOICE|現在の通話のオーディオストリームをWebsocket/SIPRECプロトコロルで送るウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/sendmessage.width-500.png" />|[Send Message](https://jp.twilio.com/docs/studio/widget-library/send-message)|MESSAGING|メッセージを送信するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/sendandwaitforreply.width-500.png" />|[Send & Wait for Reply]()|MESSAGING|メッセージを送信し、返信を待つウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/runfunction.width-500.png" />|[Run Function](https://jp.twilio.com/docs/studio/widget-library/run-function)|TOOLS & EXECUTE CODE|Twilio Functionを呼び出すウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/httprequest.width-500.png" />|[Make HTTP Request](https://jp.twilio.com/docs/studio/widget-library/http-request)|TOOLS & EXECUTE CODE|外部サービスやアプリケーションにHTTPリクエストを送信するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/Screen_Shot_2019-08-26_at_11.40.56_AM.width-500.png" />|[Add TwiML Redirect](https://jp.twilio.com/docs/studio/widget-library/twiml-redirect)|TOOLS & EXECUTE CODE|フローの外部に処理を渡すウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/Screen_Shot_2019-05-21_at_3.55.20_PM.width-500.png" />|[Send to Autopilot](https://jp.twilio.com/docs/studio/widget-library/autopilot)|CONNECT OTHER PRODUCTS|AutoPilotに通話やメッセージを送信するウィジェット|
|<img src="https://twilio-cms-prod.s3.amazonaws.com/images/send-to-flex_ZmYZLbs.width-800.png" />|[Send to Flex](https://jp.twilio.com/docs/studio/widget-library/send-flex)|CONNECT OTHER PRODUCTS|通話やメッセージをFlexに転送するウィジェット|



-------------------------------------

次の手順では`Say/Play`ウィジェットを用いて基本的なフローを設定します。

## 関連リソース

- [Twilio Stduioユーザーガイド](https://jp.twilio.com/docs/studio/user-guide)


## 次の手順
[手順2: ウィジェットをフローに追加](02-Use-Widgets.md)
