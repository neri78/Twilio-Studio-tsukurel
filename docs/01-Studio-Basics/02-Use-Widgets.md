#  手順2: ウィジェットをフローに追加

この手順では、指定したテキストまたは音声ファイルを再生できる`Say/Play`ウィジェットを例にしてウィジェットの追加方法と設定方法を学習します。


## 2-1. Say/Play ウィジェットを追加し、Triggerと接続

右側のウィジェットライブラリから`Say/Play`ウィジェットをデザインキャンバスにドラッグドロップします。

![ライブラリからウィジェットを追加](../assets/01-Widget-Library.png)

ウィジェットを追加すると画面に表示されます。

![ウィジェットが追加されている](../assets/01-Say-Play-Widget.png)

次にフローの出発点である`Trigger`ウィジェットの`Incoming Call`とSay/Playウィジェットを接続します。

![接続](../assets/01-Say-Transition.png)

これで電話が着信した際にこのウィジェットが呼ばれます。


## 2-2. Say/Playウィジェットの設定

ウィジェットをクリックすると選択状態になり、ウィジェットライブラリが設定項目の表示に切り替わります。

`Config`タブではウィジェットの設定を行えます。それぞれ下記のように変更します。

|設定項目|値|
|:----|:----|
|WIDGET NAME| Greeting |
|TEXT TO SAY| こんにちは、人生には悩みが付き物です。そんなアナタに最適なアドバイスをお送りします。|
|LANGUAGE|Japanese|
|MESSAGE VOICE| Alice、\[Polly\] Mizuki、\[Polly\] Takumiのいずれか|

一貫性を持たせるため、`MESSAGE VOICE`で選択した値をこの後でも使いましょう。

![設定画面 - Config](../assets/01-Config-Say.png)

`Transitions`タブではこのフローの接続先を設定・変更できます。今回、特に作業項目はありません。

![設定画面 - Transilations](../assets/01-Transition-Say.png)

忘れずに`Save`ボタンをクリックし内容を保存しましょう。もしボタンが押せない場合はデザインキャンバスやほかのウィジェットをクリックすると自動的に状態が保存されます。

## 2-3. 変更履歴とフローの公開

デザイン画面で変更した内容はそのつど保存されています。画面上部の変更履歴ボタンをクリックし確認できます。

![変更履歴](../assets/01-Changelog.png)

設定をすべて完了した時点で`Publish`ボタンをクリックしフローを公開します。確認ダイアログが表示されますが、続けて`Publish`ボタンをクリックします。下記のように`Flow is up-to-date`となっていることを確認します。

![フローの公開](../assets/01-Flow-Publish.png)

さて、これでフローが完成しました。次の手順でこのフローを電話番号に接続します。

## 関連リソース

- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)


## 次の手順
[手順3: 電話番号に接続](03-Connect-Flow-To-Phone-Number.md)
