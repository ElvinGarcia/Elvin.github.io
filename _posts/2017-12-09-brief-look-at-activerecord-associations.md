---
title: A Brief Look at Active Record Associations
---


##### Rail Supported Associations:
  - *belongs_to*
  - *has_one*
  - *has_many*
  - *has_many :through*
  - *has_one :through*
  - *has_and_belongs_to_many* (no need to ever use)


* `belongs_to` sets up a one-to-one connection. This also means that the foreign key is in this class . In other words `belongs_to` can ONLY go in the class that holds the foreign key. `belongs_to` relationship will be called ```yourassociationname_id```
  The `belongs_to` association supports these options:
    - :autosave
    - :class_name
    - :counter_cache
    - :dependent
    - :foreign_key
    - :primary_key
    - :inverse_of
    - :polymorphic
    - :touch
    - :validate
    - :optional

* `has_one` sets up a one-to-one connection with another model. This also means that there is a foreign key in another table that references this class. So has_one can ONLY go in a class that is referenced by a column in another table.
`has_one` supports the following options:
    - :as
    - :autosave
    - :class_name
    - :dependent
    - :foreign_key
    - :inverse_of
    - :primary_key
    - :source
    - :source_type
    - :through
    - :validate

* `has_many`
 > association indicates a one-to-many connection with another model. You'll often find this association on the "other side" of a belongs_to association. This association indicates that each instance of the model has zero or more instances of another model.

 The table with the foreign key will be declare after ` has_many` which is referred as the association table.

 `has_many` association supports these options:
    - :as
    - :autosave
    - :class_name
    - :counter_cache
    - :dependent
    - :foreign_key
    - :inverse_of
    - :primary_key
    - :source
    - :source_type
    - :through
    - :validate

* `has_many :through association` is where you create a - *through table* to act as a go-between for two models that have a many-to-many relationship.


* ` has_one :through`  one-to-one connection with another model.



* ##### Association Options
  - `:class_name` specify the class your association should **point**.
  ```RUBY
    class Post < ActiveRecord::Base
      belongs_to :author, :class_name => "User"
      belongs_to :editor, :class_name => "User"
    end
  ```
    Rails will automatically look for the foreign key named after the association, e.g. author_id or editor_id, in the Posts table and it associated with `User` method

  -  ` :foreign_key` allows you to specify the name of the foreign key name if you are not going by regular ruby naming convention.
  ```RUBY
  class User < ActiveRecord::Base
      has_many :authored_posts, :foreign_key => "author_id", :class_name => "Post"
      has_many :edited_posts, :foreign_key => "editor_id", :class_name => "Post"
  end
  ```
  - `:source` Rails uses the name of the association in the through table to determine which foreign key and table name to reach out to. If it’s named anything irregular, you’ll use the `:source` . Think of `:source` as being just like :class_name but for the associations in the “through table”.

    ```RUBY
    class Post < ActiveRecord::Base
       has_many :post_authorings, :foreign_key => :authored_post_id
       has_many :authors, :through => :post_authorings, :source => :post_author
       belongs_to :editor, :class_name => "User"
     end
 ```
  -
