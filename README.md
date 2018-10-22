[![Gem Version](https://badge.fury.io/rb/integral.svg)][version-website] 
[![Current Build Status](https://img.shields.io/circleci/project/github/yamasolutions/integral/master.svg)][ci-website] [![Inline docs](http://inch-ci.org/github/yamasolutions/integral.svg?branch=master)][docs-website]
# Integral CMS

Integral is a CMS for Rails 5+. The aim of Integral is to lower the barrier of entry in creating websites, using Ruby on Rails, with all the bells and whistles that users have now come to expect.
Out of the box integral provides;
* Backend features
    * Professional design
    * User authentication & authorization
    * Page & Post management with full WYSWIYG editing
    * Image management (w/ background image processing)
    * List management
    * Settings management
    * Activity tracking
* Frontend features
    * Dynamic Pages
    * Integrated Blog
    * SEO Ready
    * Contact form processing w/ HTML emails
    * Sitemap generation
* [Find out more...][integral-cms]

## Getting Started

1. Create a new Rails application
```
  rails new example_app --database=postgresql -T
```
2. Add Integral to your Gemfile and run `bundle install`
 ```
  gem 'integral'
 ```
3. Mount the Integral engine routes in your application
 ```
  # config/routes.rb
  mount Integral::Engine, at: "/", as: 'integral'
  root to: 'integral/static_pages#home'
 ```
4. Make sure you're app runs Integral seed data on setup
 ```
  # db/seeds.rb
  Integral::Engine.load_seed
 ```
5. Setup database - Copy and run necessary migrations
 ```
  rake integral:install:migrations
  rake db:create
  rake db:migrate
  rake db:setup
 ```
6. Run Integral install rake task (adds configuration initializers)
 ```
rails generate integral:install
 ```
7. Set the default host within the development environment, used for URL generation
```
# config/environments/development.rb

Rails.application.routes.default_url_options[:host] = 'http://localhost:3000'
```

Voila! Start your rails server and you're ready to go! You can access the user only area at `/admin`

## Information

* [Integral Website][integral-cms]
* [CHANGELOG](https://github.com/yamasolutions/integral/blob/master/CHANGELOG.md)
* [Code Documentation][docs-website]
* [Wish list](https://github.com/yamasolutions/integral/wiki/Wish-List)

### Guides
* [Deploying to production](https://github.com/yamasolutions/integral/blob/master/docs/deploying_to_production.md)
* [Integral <3 Heroku](https://github.com/yamasolutions/integral/blob/master/docs/heroku.md)
* [Extending Integral](https://github.com/yamasolutions/integral/blob/master/docs/extending_integral.md)
* [Integral Lists](https://github.com/yamasolutions/integral/blob/master/docs/integral_lists.md)
* [Integral Pages](https://github.com/yamasolutions/integral/blob/master/docs/integral_pages.md)
* [Integral Widgets](https://github.com/yamasolutions/integral/blob/master/docs/integral_widgets.md)
* [WYSIWYG Editor](https://github.com/yamasolutions/integral/blob/master/docs/wysiwyg_editor.md)

### Bug reporting
If you discover a problem with Integral, we would love to know about it. Please use the [GitHub issue tracker][github-issue-tracker] to contact us about it.

If you have discovered a security related bug, please do NOT use the GitHub issue tracker. Send an email to patrick@yamasolutions.com


### Looking for help
If you have any questions please use [StackOverflow](https://stackoverflow.com) instead of the GitHub issue tracker.


## Contributing
We love contributers! Please check out the [contributing guide][contributing-guide] for guidelines on how to proceed. Bug reports and pull requests are welcome on [Github][integral-github].


## Licence
Integral is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).


[integral-cms]: https://integralrails.com
[contributing-guide]: https://github.com/yamasolutions/integral/blob/master/docs/contributing.md
[integral-github]: https://github.com/yamasolutions/integral
[version-website]: https://rubygems.org/gems/integral
[ci-website]: https://circleci.com/gh/yamasolutions/integral/tree/master
[code-climate-website]: https://codeclimate.com/github/yamasolutions/integral
[docs-website]: https://www.rubydoc.info/github/yamasolutions/integral
[github-issue-tracker]: https://github.com/yamasolutions/integral/issues
