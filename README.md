# README

## Ruby Version
`2.4.0p0`

## Rails Version
`5.1.4`

## Prepare Rails for BDD
### Generate Rudi Rails App with PostgreSQL, skip bundle, skip-test, and skip-git
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

#### Initialize the `spec` directory
```bash
rails generate rspec:install
```

- [x] Ruby version
- [x] Rails version
- [ ] System dependencies
- [ ] Configuration
- [ ] Database creation
- [ ] Database initialization
- [ ] How to run the test suite
- [ ] Services (job queues, cache servers, search engines, etc.)
- [ ] Deployment instructions
- [ ] ...