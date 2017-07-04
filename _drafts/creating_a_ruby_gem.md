---
layout: post
title:  "Creating a Ruby GEM"
date:   2017-06-30 21:55:44 -0400
categories: Creating a Ruby GEM with Bundler
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
