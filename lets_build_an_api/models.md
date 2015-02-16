# Models

~~~ruby
class Article
    include DataMapper::Resource

    property :id, Serial

end
~~~

Now this particular model has and does nothing. We need to flesh it out.
In DataMapper we do this through properties
