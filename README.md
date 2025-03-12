# README

Steps to duplicate this project and test morph issues with Action Text / Turbo Drive Morph:
* `rails new action-text-clears-morph`
* `rails action_text:install`
* `bundle`
* `rails g scaffold Post title:string body:rich_text`
* `rails db:migrate`
* Add `validates :title, presence: true` to Post model
* Add `<%= turbo_refreshes_with method: :morph, scroll: :preserve %>` in app/views/layouts/application.html.erb above yield (line 11)
* `rails s`
* go to http://localhost:3000/posts
* Do a new, enter some text in body input, leaving title blank, submit form, resulting in body and toolbar disappearing with 422 error.
