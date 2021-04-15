# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

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


