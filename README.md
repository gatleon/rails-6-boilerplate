# rails-6-boilerplate

```
rails new rails-6-boilerplate --database=postgresql
```

Add Rubocop

```
# Gemfile
group :development, :test do
  ..
  gem "rubocop", "0.74.0"
  gem "rubocop-github", "0.13.0"
end
```

```
# .rubocop.yml

inherit_gem:
  rubocop-github:
    - config/default.yml
    - config/rails.yml
```

```
bundle exec rubocop -a
```

Add RSpec

```
# Gemfile
group :development, :test do
  ..
  gem "rspec-rails", "~> 4.0.0.beta"
end
```

```
bin/rails generate rspec:install
```

Switch to SQL Strutcure format

```
# config/application.rb
..
config.active_record.schema_format = :sql
```

```
rm -rf db/schema.rb
bundle exec rake db:create db:migrate
```

Add MountainView gem

```
# Gemfile

gem "mountain_view"
```

