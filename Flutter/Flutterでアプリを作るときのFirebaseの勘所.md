# Flutterでアプリを作るときのFirebaseの勘所

結論、複雑なアプリを作るのでなければFlutter+Firebaseで作るのが良さそう。

## 大まかなメリット

1. サーバレスでアプリ開発ができる
2. アプリ固有のめんどくさいところ(PUSH通知やクラッシュログ)にも手が届く
3. FlutterもFirebaseもGoogleが管理している

## 必須の機能

### Firebase Analytics

アクセス解析に使えるので、問答無用で入れる

### Firebase Crash Reporting

クラッシュログが取れるので、問答無用で入れる

### Firebase Cloud Messaging

PUSH通知を使うなら問答無用で入れる

## サーバを用意する前に検討すべき機能

### Cloud FireStore

RDBではなく、NoSQLのDB。リアルタイムでデータを同期してくれる(しかも簡単に！)
設計のときに、ちょこちょこ非正規化しないといけないところもあり、感じを掴むのが難しい…

### Firebase Cloud Functions


Firebase上にAPIを設置できる。Node.jsしか使えないが、Googleのサービスにはほぼアクセス可能。
無料版だと外部のAPIを叩くことはできないっぽい。

### Firebase Cloud Storage

こちらは未検証。


