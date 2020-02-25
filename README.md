<img src="https://raw.githubusercontent.com/gatleon/rails-6-boilerplate/master/gatleon-rails-6-boilerplate.png" alt="gatleon rails-6-boilerplate" align="right"/>

# rails-6-boilerplate

## Installation

Clone this repo.

```
git@github.com:gatleon/rails-6-boilerplate.git
```

Find and Replace the following instances with your application's name/pattern.

```
Rails6Boilerplate
rails_6_boilerplate
RAILS_6_BOILERPLATE
```

Run the application
```
bundle install
bin/rake db:create db:migrate
bin/rails s
```

## Alternative Installation

Follow these steps:

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

Add permitted local hosts

```
# config/environments/development.rb
config.hosts << "gat.ngrok.io"
```

Add Rack::Deflater

```
# config/application.rb

# https://www.schneems.com/2017/11/08/80-smaller-rails-footprint-with-rack-deflate/
config.middleware.insert_after ActionDispatch::Static, Rack::Deflater
```

