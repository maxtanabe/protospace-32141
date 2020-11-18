# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| -----------| ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |


### Association

- has_many :prototypesテーブル
- has_many :commentsテーブル


## comments テーブル

| Column    | Type       | Options                        |
| ----------| ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |


### Association

- belongs_to :userテーブル
- belongs_to :prototypeテーブル


## prototypes テーブル

| Column     | Type          | Options                        |
| ---------- | ------------- | ------------------------------ |
| title      | string        | null: false                    |
| catch_copy | text          | null: false                    |
| concept    | text          | null: false                    |
| image      | ActiveStorage | null: false                    |
| user       | references    | null: false, foreign_key: true |


### Association

- belongs_to :usersテーブル
- has_many :commentsテーブル
