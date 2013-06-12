Sinatra GitHub OAuth Sample
===========================

* https://github.com/shokai/sinatra-github-oauth-sample


Requirements
------------
- Ruby 1.8.7 ~ 2.0.0
- memcached


Install Dependencies
--------------------

    % brew install memcached
    % gem install bundler
    % bundle install


Config
------


### GitHub Config
[Register new Application](https://github.com/settings/applications) on GitHub

    % export GITHUB_APP_ID=abcd1234asdf
    % export GITHUB_APP_SECRET=asdf135hujikohujiko71sdfcxvoip

### Session Config

    % export SESSION_SECRET=foobar1234


Run
---

start memcache

    % memcached -vv -p 11211 -U 11211

set HTTP port 5000

    % bundle exec rackup config.ru -p 5000


Deploy on Heroku
----------------

    % heroku create --stack cedar YOUR-APP-NAME
    % heroku addons:add memcachier:dev
    % heroku config:set GITHUB_APP_ID=abcd1234asdf
    % heroku config:set GITHUB_APP_SECRET=asdf135hujikohujiko71sdfcxvoip
    % heroku config:set SESSION_SECRET=foobar1234
    % git push heroku master
    % heroku open
