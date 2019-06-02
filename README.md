# README

## usersテーブル

|column|Type|Options|
|------|----|-------|
|name|text|null: false|
|email|text|null: false|
|password|text|null: false|

### Association
- has_many: groups, through:members
- has_many: massaages
- has_many: members


## groupsテーブル
|column|Type|Options|
|------|----|-------|
|group-name|text|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many: users, through: members
- has_many: massaages
- has_many: members

##massageテーブル
|column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|text|-|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to: group
- belongs_to: user

## membersテーブル
|column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to: group
- belongs_to: user
