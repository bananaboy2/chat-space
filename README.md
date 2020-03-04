# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|index: true,null: false,unique: true|
### Association
has_many :groups,through: members
has_many :messages
has_many :members

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
### Assocoation
has_many :groups,through: members
has_many :members
has_many :messages

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|string|
|body|text|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
  belongs_to :group


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
