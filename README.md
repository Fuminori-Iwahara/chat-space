# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization


# DB設計

## Users table
|Column|Type|Options|
|------|----|-------|
|name  |string|null: false, foreign_key:true|
|email |string|null: false, foreign_key:true|

### Association
has_many:groups, through::menbers
has_many:messeages

## Group table
|Column|Type|Options|
|------|----|-------|
|name  |string|null: false|

### Association
has_many:users
has_many:messages, through::members

## members table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key:true|
|group_id|integer|null: false, foreign_key:true|

### Association
belongs_to:group
belongs_to:user

## messages table
|Column|Type|Options|
|------|----|-------|
|text  |text|null: false|
|image |string|     |
|user_id|integer|null:false, foreign_key:ture|
|group_id|integer|null:false, foreign_key:ture|

### Assocaition
belongs_to:member
belongs_to:group
* ...
