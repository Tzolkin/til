### Simulate production environment on local

Add this config to config/production.rb
```
config.assets.compile = true
config.serve_static_assets = false
config.assets.precompile += %w(*.css *.js)
```

Commands
```
$ RAILS_ENV=production bundle exec rake assets:clobber # clean assets
$ RAILS_ENV=production bundle exec rake assets:precompile
$ rails server -e production
```
