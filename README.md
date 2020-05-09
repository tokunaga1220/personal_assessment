# README
## how to use GitHub Desktop
# personal_assessment DB設計

## evaluations_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|evaluation_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|password|string|null: false|
|email|string|null: false|

### Association
- has_many :evaluations, through: :evaluations_users
- has_many :evaluations
- has_many :empoyees

## employeesテーブル
|Column|Type|Options|
|--------|----|-------|
|name|text||
|occupation|text||
|belongs|text||
|sex|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :evaluations

## evaluationsテーブル
|Column|Type|Options|
|------|----|-------|
|total_evaluation|integer|null: false|
|comment|texit|null: false|
|user_id|integer|null: false, foreign_key: true|
|emoloyee_id|integer|null: false, foreign_key: true|
### Association
- has_many :users, through:  :evaluations_users
- belongs_to :employee
- belongs_to :user