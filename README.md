![gatleon-params2](https://raw.githubusercontent.com/gatleon/rails-6-boilerplate/master/gatleon-opensource.png)

# rails-6-boilerplate

## installation

clone this repo.

```
git@github.com:gatleon/rails-6-boilerplate.git
```

find and Replace the following instances with your application's name/pattern.

```
Rails6Boilerplate
rails_6_boilerplate
RAILS_6_BOILERPLATE
```

run the application

```
bundle install
bin/rake db:create db:migrate
bin/rails s
```

## alternative installation

follow these steps:

```
rails new rails-6-boilerplate --database=postgresql
```

add Rubocop

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

add RSpec

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

switch to SQL Strutcure format

```
# config/application.rb
..
config.active_record.schema_format = :sql
```

```
rm -rf db/schema.rb
bundle exec rake db:create db:migrate
```

add MountainView gem

```
# Gemfile

gem "mountain_view"
```

add permitted local hosts

```
# config/environments/development.rb
config.hosts << "gat.ngrok.io"
```

add Rack::Deflater

```
# config/application.rb

# https://www.schneems.com/2017/11/08/80-smaller-rails-footprint-with-rack-deflate/
config.middleware.insert_after ActionDispatch::Static, Rack::Deflater
```

