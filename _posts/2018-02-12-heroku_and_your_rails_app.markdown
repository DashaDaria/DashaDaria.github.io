---
layout: post
title:      "HEROKU and your Rails App"
date:       2018-02-13 02:49:59 +0000
permalink:  heroku_and_your_rails_app
---


One of the more time consuming aspects of updating my Rails app to include jQuery frontend was my desire to deploy the app to Heroku. So I'd like to share a couple of prerequisites if you decide to do that:

Heroku does not work with sqlite, your Rails app will need to have postgresql installed. To change from sqlite to postgresql:


1. Try to avoid installing postgresql in any other way than homebrew.  
2. A good summary of the install is here -> https://www.daveferrara1.com/ruby-in-rails-switch-from-sqlite3-to-postgres/
3. Change your database.yml file to:
	
```
 default: &default
  adapter: postgresql
  encoding: unicode
  pool: 5
  host: localhost
  username: (usually your computer's user name)
  password:

development:
  <<: *default
  database: yourRails_app_name_development

test:
  <<: *default
  database: yourRails_app_name_test

production:
  <<: *default
  database: yourRails_app_name_production
```
	
	
	
4. Run rake db:setup followed by rake db:create (unlike in sqlite need this as an extra step to create the database) and finally rake db:migrate

Your app should work as before without any major issues. Make sure that there are no errors and run the Rails server.
When deploying to Heroku, you can deploy via the command line or directly through Heroku's website. The website gives you options to connect through Gtihub and deploy specific branches. Another issues I ran into when deploy was in regards to using ES6 syntax. If you are using it in your app, change the Uglifier specification in config/environments/production to:

	
	`config.assets.js_compressor = Uglifier.new(harmony: true)`
 
	 
