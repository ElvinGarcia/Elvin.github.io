---

---

##### Working With Sinatra and the MVC Architecture

Most web applications follow a similar convention in terms of their functionality and structure. In this posting I'll illustrate how a simple application follows common structures and logic found on bigger sites.

When using [Sinatra](http://sinatrarb.com/) , a [DSL](https://en.wikipedia.org/wiki/Domain-specific_language) language that uses ruby as its foundation, at its most basic level only the sinatra gem and an app.rb file is require to start running your application.

* Installs the sinatra gem
```RUBY
  gem install sinatra
```

* The 'app.rb' file will specify your application's routes and will require your sinatra gem.
  ``` RUBY
    require 'sinatra'

    get '/' do
      'Hello world!'
    end
 ```
 * Your app can be view by visiting http://localhost:4567


This is would be the most basic level of running a basic web application.

With time your applications needs will start to grow and a clean file structure will become a necessity to mananging and maintaining your application running smoothly.

A great a approach to follow is to build a [rails](https://en.wikipedia.org/wiki/Ruby_on_Rails) like file structure.

![MVCStructure]({{ site.url }}/images/MVC_file_structure.png)
