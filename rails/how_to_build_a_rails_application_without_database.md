# Build a rails application without database

To initialize a rails application without database,

```ruby
rails new my_app -O
```

It could initialize the application without `ActiveRecord`.

For existing application,

1. Remove database adapter gems.
2. Change `config/application.rb` by replacing `require 'rails/all'` with

```
require 'action_controller/railtie'
require 'action_view/railtie'
require 'active_job/railtie'
require 'rails/test_unit/railtie'
require 'sprockets/railtie'
```

or any modules you would like to require.

3. Delete your `config/database.yml` file, `db/schema.rb` and any migrations.
4. Delete migration check in `test/test_helper.rb`.
5. Delete any ActiveRecord configuration from your `config/environments` files.

## Reference

- [stackoverflow](http://stackoverflow.com/questions/19078044/disable-activerecord-for-rails-4)
- [rails/all](https://github.com/rails/rails/blob/master/railties/lib/rails/all.rb)
