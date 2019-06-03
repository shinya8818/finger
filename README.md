## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
|password_confirmation|string|null: false|
|self_introduction|text||
|sex|integer|null: false|
|img_name|string|null: false|

### Association

has_many :reactions  
has_many :chat_room_users  
has_many :chat_messages  

## reactionsテーブル

|Column|Type|Options|
|------|----|-------|
|to_user_id|integer|null: false|
|from_user_id|integer|null: false|
|status|integer|null: false|

### Association

belongs_to :user  

## chat_messagesテーブル

|Column|Type|Options|
|------|----|-------|
|chat_room|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|
|message|text|null: false|


### Association

belongs_to :user  
belongs_to :chat_room

## chat_roomテーブル

|Column|Type|Options|
|------|----|-------|

### Association

has_many :chat_messages
has_many :chat_room_users

## chat_room_usersテーブル

|Column|Type|Options|
|------|----|-------|
|chat_room|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

### Association

belongs_to :user
belongs_to :chat_room_user