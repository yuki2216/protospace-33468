# テーブル設計

## usersテーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------  |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

* has_many :prototype
* has_many :comments

## commentsテーブル

| Colum     | Type       | options           |
| --------- | ---------- | ----------------- |
| text      | text       | null: false       |
| user      | references | foreign_key: true |
| prototype | references | foreign_key: true |

### Association

- belongs_to :prototype
- belongs_to :user

## prototypesテーブル
| Colum      | Type       | options           |
| ---------- | ---------- |------------------ |
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| user       | references | foreign_key: true |

### Association

- belongs_to :user
- has_many :comments
