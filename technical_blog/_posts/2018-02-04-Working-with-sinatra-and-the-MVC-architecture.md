---
layout: post
title:  "Working With Sinatra and the MVC Architecture"
categories: Sinatra
tags: learn.co project
---

#### Working With Sinatra and the MVC Architecture

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

With time your applications needs will start to grow and a clean file structure will become a necessity to managing and maintaining your application running smoothly.

A great a approach to follow is to build a [rails](https://en.wikipedia.org/wiki/Ruby_on_Rails) like file structure.

![MVCStructure]({{ site.url }}/images/MVC_file_structure.png)

##### The app folder contains your [MVC structure](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller).
The Model-View-Controller (MVC) architectural pattern breaks down your application into three main components: the model, the view, and the controller.

 *The Model*
  > The model is responsible for your applications logic and application specifics data manipulation. It also specifies  the applications relationship with other tables and applications. Such relations are not limited to one-to-many, one-to-one and many-to-many .  

*The View*  
  > The view is responsible for the user interface. It directly interfaces with the users.

*The controller*
  > The controller is like the mediator for the controller and the view. For the most part it directs the application traffic. Controller objects can also perform setup and coordinating tasks for an application and manage the life cycles of other objects.

*Helper Folder*
  > The helper folder is conventionally used to host shared code among classes. Such shared code included modules codes that are shared through out your application.

*Config*
  > Config folder host the require other files and gem for your application environment. In most cases it also includes your database adapter.

*db*
  >DB folder host your database and table schema(structure). Beside containing these crucial files it hosts generated migrations that where used to manipulate your tables.

*lib*
  >Lib folder as the name suggest conventionally host created libraries or library obtain from other models to data manipulation.

*config.ru*
  > Config.ru files is used to wrap your application together. As a result this file will require the files in the config folder that host your environment configurations and acquire other vital files, gem and libraries. Here is where you tell your application where the files for the MVC architecture are located.

*Gemfile*
  >[Gemfile](https://bundler.io/) acquires all the third party gems that your application will be using. Such gems might include Sinatra, ActiveRecord, Shotgun and testing apps like Pry, and Tux

*Rakefile*
  > [Rakefile](https://en.m.wikipedia.org/wiki/Rake_(software) ) is used to create task for your application. These task include the task of creating migrations, entering a testing console and many more. You could either create your own process or acquire rake task from gems and integrate them in your rake file such as the ```sinatra-activerecord``` gem. Typing ```rake -T``` in your console displays all available rake task.
