## やりたいこと

- GooglePhotoの写真を取得し、Lineへ送信する。週に1回送信をする
- フォトフレームに送信するなどできます。
- 3日間ほどかかった。。。世界中の先人たちに感謝


## 環境
Gas
Line

## 初期ロードマップ
- 1　アルバム名を取得
 - 1-1　googlePhotoで取得したアルバム名をgooglespreadsheetのセルへ一覧で書き出す
 - 1-2　共有アルバムのIDを取得し、googlespreadsheetのセルへ一覧で書き出す 

- ３　画像をURLで保持
- 4　Lineへ送信
 - 4-1 sampleLine送信する(テキスト)
 - 4-２ sampleLine送信する(URL化の画像一枚)
 - 4-３ Line送信する(URL化の画像一枚)

## ソースは以下のMain。
https://github.com/hide6974/GoogleGas/blob/main/main.gs

コツはちいさくできることから少しづつやることでしたね。

PropertiesService.getScriptProperties().getProperty　→最初はこの意味が不明。3時間後プロパティかと納得

作成は、以下を利用。

https://qiita.com/hiteto/items/f63584045df31dff31d2
