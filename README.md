# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version
　Ruby 2.6.5
* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
## 概要

無計画旅行(友達含め本人)や何もすることない休日のぷらっと過ごす日に使える新しい発見になる
日常型トリップbookのようなアプリ

## URL
 https://maphoto.herokuapp.com/

## 使用技術
 Ruby 2.6.5
 rails 6.0.0
 mysql2 0.4.4
 puma
 sass-rails
 webpacker
 turbolinks
 jbuilder
 rubocop
 devise

## 機能一覧

ユーザー登録、ログイン(devise)
投稿機能、画像投稿
カテゴリー機能
コメント機能

## 利用方法
東京に（例）に遊びに来た人、またはその人をもてなす人
あとは何も予定のない休日にふらっと知らない場所を探して行ってみたい人が
インスタグラムのように写真でインスピレーションで誰かが行った
おすすめの場所を簡単に見つけられるサイト

## 目指した課題解決
わざわざtrip bookを買わなくてもよく
ローカルの人やコアなスポット、その時期おすすめの場所を
簡単に写真で発見できて場所検索できる

## 洗い出した要件
user
comment
post
image
後がgoogl mapにつなげたい

## 実装した機能についての画像やGIFおよびその説明 / 実装予定の機能 / ローカルでの動作方法
未完成
## テスト
単体テスト(model)








## users テーブル

| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| nick_name       | string | null: false |
| email           | string | null: false, unique: true |
| encrypted_password        | string  | null: false |

### Association
- has_many :post dependent: :destroy
- has_many :comment dependent: :destroy


## post テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| description        | text   | null: false |
| category_id        | integer | null: false |
| place              | text    | null: false |
| user               | references | null: false, foreign_key: true｜


### Association
- belongs_to :user 
- has_many :comment dependent: :destroy

## comment テーブル

| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| description     | text   | null: false |
| post            | references | null: false, foreign_key: true |
| user            | references | null: false, foreign_key: true |

- belongs_to :post 
- belongs_to :user 


