# README


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association

 has_many :users,through: :groups_users
 has_many :groups_users
 has_many :messages

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
 has_many :groups,through: :groups_users
 has_many :groups_users
 has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|string|
|image|string|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user

