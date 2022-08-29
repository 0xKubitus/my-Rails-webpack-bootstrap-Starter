# update Ruby version
$ rvm install 2.7.1
...
$ ruby -v
ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-darwin19]
# update Node version
$ nvm install 14.8
...
$ node -v
v14.8.0
# install Yarn
$ npm install -g yarn
...
$ yarn -v
1.17.3
# install Rails
$ gem install rails
$ rails -v
Rails 6.0.3.2

#############################################

# CREATE THE APP 
$ rails _6.1.6_ new rails+webpack+bootstrap_demo --database=postgresql --webpack

# Quick scaffold for creating the 'Article' 
$ rails generate scaffold Article title:string content:text

# create db and do migrate
$ rails db:create db:migrate 
# start server
$ rails s

## Now we should have a page in localhost:3000/posts

# Install Bootstrap with yarn , from Bootstrap 5 we don't need JQuery anymore.

$ yarn add bootstrap@next
$ yarn add @popperjs/core

