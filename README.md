# README

## Users_Table

|Column|Type|Options|
|------|----|-------|
|email|string|not_null,unique|
|encrypted_password|string|not_null|
|name|string|not_null|
|profile|text|not_null|
|occupation|text|not_null|
|position|text|not_null|

##Association
has_many :prototypes
has_many :comments
## Prototype_Table

|Column|Type|Options|
|------|----|-------|
|title|string|not_null|
|catch_copy|text|not_null|
|concept|text|not_null|
|user|references|not_null,foreign_key|

##Association
belongs_to :user
has_many :comments

## Comments_Table

|Column|Type|Options|
|------|----|-------|
|content|text|not_null|
|prototype|references|not_null,foreign_key|
|user|references|not_null,foreign_key|

##Association
belongs_to :user
belongs_to :prototype