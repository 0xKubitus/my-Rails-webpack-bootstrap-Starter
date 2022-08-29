## 1st step: checking your ruby, rails, node & yarn versions:

These are the minimal versions to use:

##### update Ruby version
$ rvm install 2.7.1
...
$ ruby -v
ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-darwin19]
##### update Node version
$ nvm install 14.8
...
$ node -v
v14.8.0
##### install Yarn
$ npm install -g yarn
...
$ yarn -v
1.17.3
##### install Rails
$ gem install rails
$ rails -v
Rails 6.0.3.2



## 2nd step: CREATE THE APP 
$ rails _6.1.6_ new rails+webpack+bootstrap_demo --database=postgresql --webpack

#### -> Quick scaffold for creating the 'Article' 
$ rails generate scaffold Article title:string content:text

##### create db and do migrate
$ rails db:create db:migrate 

#### start server
$ rails s

### => Now we should have a page in localhost:3000/posts

##### Install Bootstrap with yarn 
###### (from Bootstrap 5 we don't need JQuery anymore)

$ yarn add bootstrap@next

$ yarn add @popperjs/core




## Import Bootstrap styles through Javascript styles by updating the application layout 'app/views/layouts/application.html.erb'

##### add this new line
`<%= stylesheet_pack_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>`
##### at the bottom in the head tage, so it looks like:
```html
<head>
  <title>BootstrapDemo</title>
  <%= csrf_meta_tags %>
  <%= csp_meta_tag %>
  <%= stylesheet_link_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
  <%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
  <%= stylesheet_pack_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
</head>
```

###### *Notice the new tag we added is stylesheet_pack_tag instead of the existing stylesheet_link_tag already there.*
###### *This new tag will import the styles sheets from 'app/javascript/packs/*.js' in this case, it will import styles from 'app/javascript/packs/application.js'*



## Next, we need to import bootstraps to our 'application.js'

##### create a new folder at: 'app/javascript/stylesheets'.
We will then put our stylesheets in here and they will be managed by webpack

##### create new file: 'app/javascript/stylesheets/application.scss'
##### inside this file, add this line:
@import "bootstrap"

##### in file app/javascript/packs/application.js, at bottomm of the file, add:
import "bootstrap"
import "../stylesheets/application"
