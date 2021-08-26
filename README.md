# テーブル設計

## users テーブル

| Column     | type   | options     |
|------------|--------|-------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

- has_many :prototypes
- has_many :comments



## prototypes テーブル

| Column     | type           | options     |
|------------|----------------|-------------|
| title      | string         | null: false |
| catch_copy | text           | null: false |
| concept    | text           | null: false |
| image      | Active Storage |             |
| user       | references     |             |

- belongs_to :user
- has_many :comments



## comments テーブル

| Column     | type         | options     |
|------------|--------------|-------------|
| text       | text         | null: false |
| user       | references   | null: false |
| prototype  | references   | null: false |

- belongs_to :user
- belongs_to :prototype