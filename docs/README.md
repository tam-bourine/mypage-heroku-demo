# 概要
## Salesforceと連携する会員サービスサイトを構築したい方へ
- Salesforceで会員サイトを簡単に作成できるWebアプリです。
- 導入することで以下のような課題を解決することができます。

### 1.Salesforceの顧客のみに特別な情報、サービスを提供することができていない。
- 顧客だけが利用できるようにするためのログイン機能がついています。
- ログインすることで特別な情報を閲覧することができます。

### 2.WEB上で顧客が入力した情報や、行動履歴情報がSalesforce上で確認できていない。
- 会員登録機能や、各種フォームをクイックに構築するフォーマットを用意しています。
- 入力された内容はSalesforceに情報登録され、管理者に登録があったことを通知しますので、顧客のWEB上での活動をリアルタイムに知ることができます。

### 3.Salesforceで管理しているデータをWEB上にも反映し、顧客に閲覧してほしい
- Salesforceのオブジェクトに登録された内容をWEB上に表示することができる簡易なCMS機能が　　ついています。わざわざHTMLを編集する必要はありません。

# 必要な環境
- Salesforce環境
- Herokuアカウント

# セットアップ方法
### 1.Salesforceの非管理パッケージをインストールする
- こちらからSalesforceにパッケージをインストールします

### 2.Herokuにアプリを作成して、Heroku PostgresとHeroku connectをプロビジョンする
```
$ heroku create <app name>
$ heroku addons:create heroku-postgresql:hobby-dev --app <app name>
$ heroku addons:create herokuconnect --app <app name>
```

### 3.Heroku connectを設定する
- 1.で作成したSalesforce組織に対して接続設定を行い、information__cをマッピングする。
- ※接続設定時にDBのスキーマ名はpublicにする ※Heroku connectの設定はこちら

### 4.Herokuにデプロイする
```
$ heroku git:remote -a <app name>
$ git push heroku master
```

### 5.Herokuアプリにアクセスする
- Salesforceのお知らせオブジェクトにコンテンツを登録すると、即座にWebアプリ側に反映されます。