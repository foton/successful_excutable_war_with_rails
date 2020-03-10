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

