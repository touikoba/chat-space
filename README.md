## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false, index: true|
### Association
- has_many :posts
- has_many :groups_users
- has_many :groups, through :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :posts
- has_many :groups_users
- has_many :users, through :groups_users

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group