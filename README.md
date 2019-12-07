## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|references|null: false, foreign_key: true|
|tweet_id|references|null: false, foreign_key: true|
### Association
- belongs_to :tweet
- belongs_to :user

