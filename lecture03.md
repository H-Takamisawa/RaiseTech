# 第3回課題

## 概要

1. APサーバーについての結果
2. DBサーバーについての結果
3. 感想

## 内容

### 1. APサーバーについての結果

- APサーバー起動時の画面

![デプロイ結果](images/lecture03/01_1_Apserver_deploy.png)

- APサーバーの名前：puma
- バージョン：6.4.2

![pumaのバージョン](images/lecture03/01_2_puma_version.png)

- APサーバーを終了させた場合、引き続きアクセスできますか？   →アクセス不可

![puma終了時](images/lecture03/01_3_Apserver_stop.png)


### 2. DBサーバーについての結果

- DBサーバーの名前：Mysql
- バージョン：8.0.36

![DBサーバーのバージョン](images/lecture03/02_1_DBserver_version.png)

- DBサーバーを終了させた場合、引き続きアクセスできますか？   →アクセス不可

![Mysql終了時](images/lecture03/02_2_DBserver_stop.png)

- DBサーバーを再度起動したら、アクセス可能となりました。

![Mysql再起動](images/lecture03/02_3_DBserver_start.png)

- Railsの構成管理ツールの名前：Bundler

![bundlerの説明](images/lecture03/03_1_bundler.png)

![Gemfile](images/lecture03/03_2_Gemfile.png)

### 3.感想

- コマンド自体は短く理解できるものでも、実行したときに何が起こっているのかを理解するのはとても難しいと感じました。
  エラー文を読み解くのも一苦労であると感じました。

- スペルミスに気付かずにエラー対処に時間が掛かったので、人のミスを減らすために何が出来るかを考えることも大事だと思いました。

- まだまだ理解できていない部分が多かったり、Git操作もまだ慣れていないので録画授業の見直しなどで復習も欠かさないようにしようと思いました。