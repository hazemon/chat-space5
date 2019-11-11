## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|
|user_id|integer|

### Association
- belongs_to :group
- belongs_to :user

### Usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|E-mail|string|null: false, foreign_key: true|

### Association
- has_many :groups :through :groups_users
- has_many :groups_users
- has-many :messages

### groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|

### Association
- has_many :users :through :groups_users
- has_many :groups_users
- has_many :messages


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
