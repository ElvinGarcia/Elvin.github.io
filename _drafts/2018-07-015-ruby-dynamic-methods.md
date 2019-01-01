---
layout: post
title:  "Ruby Dynamic Mehods"
categories: RUBY
tags: ruby dynamic methods define_method grep $1

---

### Dynamic Methods

  Ruby is know for being a very friendly language to use and learn has beginners language. Ruby could be as complex as it could be a joy to use.
  One of such method that encompasses this is 'define_method'.
  Define_method is a private method that defines instant method on the spot.
  You just need to provide a method name and a block, which becomes the method body.
   ```
    class MyClass
      define_method :my_method do |my_arg|
        my_arg * 3
      end
    end
    obj = MyClass.new obj.my_method(2) # => 6
   ```
   
