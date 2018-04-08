---
layout: post
title:  "Ruby Style Guide "
categories: RUBY
tags: ruby shopify
---

### Ruby Style Guide Suggestions (According to Shopify)

*  Make all lines of your methods operate on the same level of abstraction also known as Single Responsibility Principle (SRP). *(Single Level of Abstraction Principle)*

   By making each have a single functionality or responsibility not only leads to better organized code but for better readability and refactoring.
   In layman terms, its like having a registration object that:
    - Checks the IP address in a spam database,
    - Sends an email to the new user,
    - Adds a bonus to an account of a recommending user,
    - Creates accounts in related services,
    and many more.

    Instead of having a separate method for each action and calling them individually.

  ```RUBY
  class RegistrationController < ApplicationController
      def create(params)
        user = User.create(params)
        if user.valid? && ip_valid?(registration_ip)
          user.save!
          user.send_email
          user.refer_bonus
          user.related_services
        end
      end
  end
  ```
    wrong

    ```RUBY

    class RegistrationService
        def start(params)
          user = User.new(params)
          if user.valid? && ip_validator.valid?(registration_ip)
            user.save!
            after_registered_events(user)
          end
          user
        end

        private

        def after_registered_events(user)
            Mailer.new(user)
            Referal.new(user)
            Services.new(user)
        end

        def ip_validator(registration_ip)
          @ip_validator ||= IpValidator.new
        end
     end

      class RegistrationController < ApplicationController
        def create
          user = RegistrationService.new.fire!(registration_params)
        end

      end
    ```
    good

      Why is the refractor code good ? Beside being more organized if we needed to change any part of the registration events we would do so in its individual class. This makes the code easier to maintain and read has well.


* Code in a functional way. Avoid mutation *(side effects)* when you can.

```
[example goes here ]
```

* Do not program defensively
```
[example goes here ]
```

* Do not mutate arguments unless that is the purpose of the method
```
[example goes here ]
```


* Do not mess around in / monkeypatch core classes when writing libraries.
```
[example goes here ]
```

* Keep the code simple.
```
[example goes here ]
```

* Don’t overdesign.
```
[example goes here ]
```

* Don’t underdesign.
```
[example goes here ]
```

* Avoid bugs.
```
[example goes here ]
```

* Be consistent.
```
[example goes here ]
```

* Use common sense.
```
[example goes here ]
```
