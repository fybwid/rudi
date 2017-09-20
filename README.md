# README

## [Ruby](https://www.ruby-lang.org/en/) Version
`2.4.0p0`

## [Ruby on Rails](https://rubyonrails.org/) Version
`5.1.4`

## Prepare Rails for BDD
### Generate Rudi Rails App with [PostgreSQL](https://www.postgresql.org/), skip bundle, skip-test, and skip-git
```bash
rails new rudi -d postgresql -B --skip-bundle -T --skip-test -G --skip-git
```

#### Install Gems Locally
```bash
cd rudi && bundle install --path vendor/bundle
```

### Add [Rspec Rails](https://github.com/rspec/rspec-rails) gem to the development and test groups
```ruby
group :development, :test do
  gem 'rspec-rails', '~> 3.6'
end
```

#### Install Gem Locally
```bash
bundle install --path vendor/bundle
```

#### Initialize the `spec` directory
```bash
rails generate rspec:install
```

#### Add Shoulda Matchers gem Configuration
Open `spec/rails_helper.rb` and add the following configuration to the end:
```ruby
  Shoulda::Matchers.configure do |config|
    config.integrate do |with|
      with.test_framework :rspec
      with.library :rails
    end
  end
```

### Add [Factory Girl](https://github.com/thoughtbot/factory_girl) Gem
```bash
group :development, :test do
  gem 'rspec-rails'
  gem 'factory_girl_rails'
end
```

#### Install Gem Locally
```bash
bundle install --path vendor/bundle
```

### Add [Cucumber](https://github.com/cucumber/cucumber-rails) Gem
```bash
group :test do
  gem 'shoulda-matchers'
  gem 'cucumber-rails', require: false
  gem 'database_cleaner'
end
```

#### Install Gem Locally
```bash
bundle install --path vendor/bundle
```

#### Bootstrap the application with Cucumber
```bash
rails generate cucumber:install
```

### Add [Selenium Webdriver](https://github.com/SeleniumHQ/selenium/tree/master/rb) Gem
```bash
group :test do
  gem 'shoulda-matchers'
  gem 'cucumber-rails', require: false
  gem 'database_cleaner'
  gem 'selenium-webdriver'
end
```

#### Install Gem Locally
```bash
bundle install --path vendor/bundle
```



- [x] Ruby version
- [x] Rails version
- [ ] System dependencies
- [x] Configuration
- [ ] Database creation
- [ ] Database initialization
- [ ] How to run the test suite
- [ ] Services (job queues, cache servers, search engines, etc.)
- [ ] Deployment instructions
- [ ] Documentation ([Rdoc](https://github.com/ruby/rdoc), [Yard](https://yardoc.org/))
- [ ] ...