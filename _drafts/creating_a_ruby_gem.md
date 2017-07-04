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
