Purpose - Listed below are gems that have post installation steps.
Some steps if repeated may result in undesired results e.g. duplicate seed data in database.

Audience - Developers, deployer.

Developers! Pls update file as you work down develop branch!

Note - [Initial] refers to [v0.0.0]

[Initial]
gem 'solidus', '1.2.2'
gem 'solidus_auth_devise'
Post install
rails g spree:install --migrate=false --sample=false --seed=false # this step creates spree initializer file spree.rb, etc ...
                                                                  # appends seeds.rb ...
                                                                  # and runs bundle exec rake railties:install:migrations
bundle exec rake db:migrate
bundle exec rake db:seed
bundle exec rake spree_sample:load
