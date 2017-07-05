---
layout: post
title:  "Creating a Ruby GEM"
date:   2017-06-30 21:55:44 -0400
categories: Creating a Ruby GEM with Bundler
tags: learn.co project
---           

# Creating a Ruby Gem with Bundler

Creating a Ruby gem could an intimidating task but a well worth it goal to pursue. I"ll be going over on how to get started, the structure of it all and eventually publish your newly minted gem.

## Gem File structure
To get a better understanding of gem's structure we will go over the methodical structure it gems require. We will start by creating a gem with bundler which is a gem manager. More information on [Bundler](https://bundler.io/) can be found at the following link. [https://bundler.io/Bundler](https://bundler.io/)

We will start by creating an app 'app_name'.
Once we open up terminal on a mac and navigate to the directory we want our gem to reside we type the following

    `bundle gem app_name`

Once that completed you should have a similar file structure as the following

   ![GemStructure]({{ site.url }}/images/RubyGem_File_Structure.png)

   {%include creating_a_ruby_gem_table.html%}


## Requiring files

The first step in creating a ruby gem is requiring the necessary files for your environment. What this means is telling your gem what files it should know about. I place this code in the the lib directory/product_review.rb
On my product_review gem I required the following files.


      require "nokogiri"
      require "open-uri"
      require "pry"
      require_relative "../lib/product_reviews/version"
      require_relative "../lib/product_reviews/scraper"
      require_relative "../lib/product_reviews/catagories"
      require_relative "../lib/product_reviews/product_controller"
      require_relative "../lib/product_reviews/board"

#### ProTip
>  `Always use require_relative when requiring file.
    Typically require is used when requiring from Ruby's standard library.`

  Once that is settle we could start requiring any other gems that our gem will depend on. We will specify these gems in our Gemfile.

  After we taken care of our gem dependencies we could start writing our code inside the directory with the same name as our gem inside the lib directory.
  in my case that would be `lib/product_reviews`

  I would writing each class in individual files with the *.lib* extension and making sure telling my gem that the file exist by requiring it in the *product_reviews.rb* file inside the lib directory.


#### ProTip
  >  `When using git make sure to commit often and write often.`

  Once your code is in place and passing its time to setup your executable.
  In your *bin* directory you will find two file. Console and setup will play a major part in executing your gem.

## bin/console
  The console file is used to experiment with your could before releasing it. It allows us to set an experimental environment to test our gem.

  ![bin-console](/images/bin-console.png)

  The console file doesn't require any extension since it will be interacting directly with the terminal. As a result we need to specify exactly where it can find our ruby interpreter, in order to interpret our code. As show on line one on the above picture.  
  This works because most modern systems have an executable at
  > `#!/usr/bin/env ruby `

  Which will execute the utility that you pass to it based on your path.
  Line 3 , 4 and 5 are requiring irb session and the file that holds all the paths to the file containing the ruby code that was previously written.
  Line 16 starts the IRB session. This simple setup allows me to test my code in IRB before deploying it.

## First call
  When first executing our gem the first file that gets run is located in
  > `bin/product_review`

  The code looks like this

> ` #!/usr/bin/env ruby `
>
> ` require_relative"../config/environment" `
>
> ` ProductReviews::ProductController.new.call `

The first line tells the terminal where to search for the ruby interpreter while the second lines loads our ruby environment which contains the path to all our files necessary to run this gem. The third line creates an object and executes the instance method `call`. Since this object will mostly be responsible for the flow of out program it's only valid that in most cases it's refer as controller, hence ProductController.

#### ProTip
>  Since we are working directly with the systems CLI it's logical to expect the system to protect its self from hard by not giving out `bin/product_review` file execucable permission. This can easily be change by run

  > `chmod +x file_name`

>  and

  > `s –l `

  To check the file permission.

## Some Best Practice

  * Try to write has abstract as possible. This will allow for better maintainability and when adding features.

  * Try to follow the DRY principle. Don't repeat yourself.

  * Don't ever give up
