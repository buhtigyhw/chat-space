# README

# DB設計

## users table

| Column         | Type           |Options        |
| :------------- | :------------- |:------------- |
| name           | string         |:null: false, unique: true, index: true|

### Association
- has_many :messeages
- has_many :group_users
- has_many :groups, through: :group_users

## groups table

| Column         | Type           |Options        |
| :------------- | :------------- |:------------- |
| name           | string         |:null: false, unique: true|

### Association
- has_many :messeages
- has_many :group_users
- has_many :users, through: :group_users

## group_users table

| Column         | Type           |Options        |
| :------------- | :------------- |:------------- |
| user           | references     |:null: false, foreign_key: true|
| group          | references     |:null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

##messages table
## messages table

| Column         | Type           |Options        |
| :------------- | :------------- |:------------- |
| body           | text           |               |
| image          | string         |               |
| user           | references     |:null: false, foreign_key: true|
| group          | references     |:null: false, foreign_key: true|

##Association
### Association
- belongs_to :user
- belongs_to :group
