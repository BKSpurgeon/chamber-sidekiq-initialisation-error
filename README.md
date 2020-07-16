# README

The problem is that Chamber is not being recognised in the sidekiq.yml file.

**Setting up**

```ruby
gem "chamber"

gem 'sidekiq'
```

**1. What is Chamber?**

Chamber allows you set some variables in the `config/settings.yml` file. These variables are then made available via `Chamber.env.variable_i_have_set_in_the_config_file`.

Here is a snippet of this `config/settings.yml` file (not to be confused with the sidekiq.yml file):

```yml
development:
  sidekiq_concurrency: 5

test:  
  sidekiq_concurrency: 5

production:  
  sidekiq_concurrency: 5
```

**2. Setting Chamber variable in a YAML file**

Spin up a rails console session:

```terminal
rails c
Chamber.env.sidekiq_concurrency # => 5
```

**3. Run `bundle exec sidekiq`**

Here is the error: WARN: NameError: uninitialized constant Chamber

2020-07-16T03:01:23.284Z pid=19958 tid=gsqyiai6q WARN: NameError: uninitialized constant Chamber