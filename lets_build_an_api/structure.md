# Structure

It always a good practice to define a structure for the application. Which folders go there, which files go here and so on.

For this project we will use the following structure:

* Gemfile
* Rakefile
* app.rb
* models/
* routes/

Let's go over each of the items:

**Gemfile**: As we explained in Section 3.1, Ruby uses gems to reuse functionality. In the Gemfile, we list all the libraries we are going to use in the project

~~~ruby
#Gemfile
source 'http://rubygems.org'

gem "sinatra"
gem "data_mapper"
gem "dm-sqlite-adapter"
gem  "json"
~~~

Here we have the Sinatra gem, as well as DataMapper and its Adapter for Sqlite. We also include the JSON gem since we are going to consume and feed the API through JSON.

**Rakefile**: The Rakefile is where we store some useful tasks for the application, for example migrate new changes into the database without stopping the server and listing our routes, which will become of great importance when we document our API.

~~~ruby
desc "List all routes for this application"
task :routes do
  puts `grep '^[get|post|put|delete].*do$' routes/*.rb | sed 's/ do$//'`
end
~~~
To execute any task, just type `rake TASK_NAME`.

**app.rb**: This is the most important file in the entire application. This is the file you run to fire up the server.

~~~ruby
require 'rubygems'
require 'sinatra'
require 'data_mapper'
require 'json'

DataMapper.setup(:default, "sqlite3://#{Dir.pwd}/dev.db")

require './models/init'
require './routes/init'

DataMapper.finalize.auto_upgrade!
~~~
It's going to require all the gems it needs and then sets up the database. Immediately after, it calls all the models and routes we define and then it finalize this construction process. In essence, all our structure could collapse to this single file, and nothing would change.

**models/**

In this folder we are going to define all our models, which are just Ruby classes. For convinience, we will define a single `init.rb` file, which will require all models in this folder. In turn, and as you can see above, `app.rb` requires this `init.rb` file.

~~~ruby
#models/init.rb
#The line require_relative './MODEL_NAME.rb' goes as many models you have
require_relative './movie'
require_relative './director'
~~~

**routes/**

Following the same idea as the model folder, here we will also have an `init.rb` file.

~~~ruby
#The line require_relative './MODEL_NAME_PLURAL.rb' goes as many models you have
require_relative './movies'
require_relative './directors'
~~~

All routes for a given model, will be placed in a different file.

----

It is important to note that there's no single official structure for a Sinatra app, so I have chose this one for the project. It is inspired in both [Tomaszj's sample](https://github.com/tomaszj/sinatra-datamapper-sample) and [crojasaragonez's service ](https://bitbucket.org/crojasaragonez/sinatra_service).

Now that with have the skeleton in place, it's time to create our models!
