already tried:
1) `rails new app_name`
   `cd app_name`
   `warble`     => ERROR already activated ruby zip 2.2.0 (warbler needs 1.3.0)
2) Forcing rubyzip 1.3.0 in Gemfile
   `warble`     =>  succesfull
   `warble executable war`     =>  succesfull
   running excutable war `java -jar app_name.war`:
    - started succesfully
    - request to `localhost:8080` ends with rails version of 404
    (`2020-03-10 09:43:26.930:INFO:/:qtp1296064247-12: F, [2020-03-10T09:43:26.929779 #14285] FATAL -- : [2877d697-2ee1-4264-bb1c-dfb99fffc718] ActionController::RoutingError (No route matches [GET] "/"):|`)
    - running `bundle exec rails s` and opening `loclhost:3000` displays correctly page "Yay! You are on Rails"
3) Creating root path
     `bundle exec rails g controller Home index` + adding `root 'home#index'` to `config/routes.rb`
     warbling successfull, run of WAR ends on `FATAL -- : [ade6a889-3b46-4dc8-9352-de4c9135694f] ActionView::Template::Error (The asset "application.css" is not present in the asset pipeline.):|`


