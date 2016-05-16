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

[v0.1]
gem 'solidus_gateway', '~> 1.0', '>= 1.0.1'
Post install
rails g solidus_gateway:install
->  run  bundle exec rake railties:install:migrations FROM=solidus_gateway from "."
      Copied migration 20160514021119_create_skrill_transactions.solidus_gateway.rb from solidus_gateway
      Copied migration 20160514021120_update_braintree_payment_method_type.solidus_gateway.rb from solidus_gateway
      Copied migration 20160514021121_update_stripe_payment_method_type.solidus_gateway.rb from solidus_gateway
      Copied migration 20160514021122_update_balanced_payment_method_type.solidus_gateway.rb from solidus_gateway
      Copied migration 20160514021123_update_paypal_payment_method_type.solidus_gateway.rb from solidus_gateway
      Copied migration 20160514021124_migrate_stripe_preferences.solidus_gateway.rb from solidus_gateway
      Would you like to run the migrations now? [Y/n]

gem 'braintree', '~> 2.60'
Post install
none

gem 'spree_mail_settings', :path => './gem_hack/spree_mail_settings-2-4'
Post install
none
Hacked spree_mail_settings-2-4 gem resides in gem_hack dir.
As gem_hack dir been excluded from git ( .gitignore modified to
include line /gem_hack), you will need to manually create gem_hack
dir ( on par level with dirs app, db, config, etc ...), and then
copy spree_mail_settings-2-4 into gem_hack.
Copy of spree_mail_settings-2-4 is given by below path
  /home/jerry/dev/me/solidus_store/gem_hack/spree_mail_settings-2-4
