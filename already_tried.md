already tried:
1) `rails new app_name`
   `cd app_name`
   `warble`     => ERROR already activated ruby zip 2.2.0 (warbler needs 1.3.0)
2) Forcing rubyzip 1.3.0 in Gemfile
   `warble`     =>  successful
   `warble executable war`     =>  successfull
   running excutable war `java -jar app_name.war`:
    - started successfully
    - request to `localhost:8080` ends with rails version of 404
    (`2020-03-10 09:43:26.930:INFO:/:qtp1296064247-12: F, [2020-03-10T09:43:26.929779 #14285] FATAL -- : [2877d697-2ee1-4264-bb1c-dfb99fffc718] ActionController::RoutingError (No route matches [GET] "/"):|`)
    - running `bundle exec rails s` and opening `loclhost:3000` displays correctly page "Yay! You are on Rails"
3) Creating root path
     `bundle exec rails g controller Home index` + adding `root 'home#index'` to `config/routes.rb`
     warbling successful, run of WAR ends on `FATAL -- : [ade6a889-3b46-4dc8-9352-de4c9135694f] ActionView::Template::Error (The asset "application.css" is not present in the asset pipeline.):|`
4) Precompiling assets
    `bundle exec rake assets:precompile`
    warbling successful, request to `localhost:8080` displays page with "Home#index \n Find me in app/views/home/index.html.erb"!
    YEAAAH!
5) Adding scaffold for League (SQLite database)
   `bundle exec rails g scaffold league name:string`
   Jruby run fully functional, warbling OK , but run from WAR ends with
   `(ActiveRecord::JDBCError: org.sqlite.SQLiteException: [SQLITE_ERROR] SQL error or missing database (no such table: leagues): SELECT "leagues".* FROM "leagues"):|`
6) Copied `db/development.sqlite` to `db/production.sqlite3`
   Everything up and running. From WAR run, I can add new league. BUT (surprise, surprise!) it will not hold to next start of WAR (muhehe!).



