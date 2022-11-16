# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

- Ruby version
  3.0.0
- System dependencies

- Configuration

- Database creation

- Database initialization

- How to run the test suite

- Services (job queues, cache servers, search engines, etc.)

- Deployment instructions

- ...

THe frond end: Destroying (deleting) articles
REST - Representational state transfer -mapping HTTP verbs (get, post, put/patch, delete) to CRUD actions
resources provides REST-ful routes to Rails resources
show, index, new, create, edit, update, destroy.

DRY dode: do not repeat yourself

- re-facting
- extract away the redundancies in code

CRUD

- rails generate scaffold Article title:string description:text
- rails generate scaffold User username:string
- rails db:migrate
- rails routes --expanded
- rails generate migration create_articles
- rails db:migrate

rails console CRUD

- rails console
- Article.create(title: '', description: '')
- article = \_
- article.save
- Article.create(title: '', description: '').save
- Article.find(3)
- Article.first
- Article.last
- article = Article.find(3)
- article.title
- article.description
- article.description = ''
- article.title = ''
- article.destroy

database validate
in article.rb :
validates :title, presence: true, length: { minimum: 6, maximum: 100 }
validates :description, presence: true, length: { minimum: 10, maximum: 300 }

one to many associations

- rails generate scaffold User username:string
- rails console
- User.create(username: " ")
- User.create(username: " ")
- quit
- rails generate migration add_user_id_to_articles
- add_column :articles, :user_id, :int
- has_many :articles
- belongs_to :user
- rails console
- user_1 = User.first
- article = Article.last
- user_1.articles << article
- Article.create(title: "", description: "", user_id: user_1.id)
- Article.create(title: "", description: "", user: user_1)
- user_1.articles.build(title: '', description: '')
- user_1.articles

git branch and merge

- git checkout -b 'branchName'
- rails generate migration create_users

Permissions functionality
Admin users, moderators, regular users etc.
CRM apps - permisions table
Permissions field (String) - with values such as admin, moderator
Admin column (boolean) - simplest solution

add_admin_column
rails generate migration add_admin_to_users

Many to many associations:
Automated testing - unit, functional, integration

1. doctors and patients
2. projects and emplyees
3. social miedia: followers and followee's

Unit tests Models, individual units of the application (like a validation) are working

Functional tests: controllers, a function is working, for example is before_acrion stopping a non-logged in user from performing an action

Integration tests: Full features, start to finish of a business process, example: a user signs up for the app

Functional Tests
Categories controller:
-new category - new form (new.html.erb)
-show category - show.html.erb
-categories index (list) - index.html.erb

Ruby on Rails Components
frount-end, back-end etc.
-Associations, on to many, many to many
-Front-end implementation and styling
-Back-end implementation, REST
-Git, GitHub, local dev and production (Heroku)
