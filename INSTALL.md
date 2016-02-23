# ruby-style-guide gem
This repo has been configured as a gem so it can be easily integrated into rubocop configurations for our projects.

To use this you would first need to update the **Gemfile** of a project like so...

```ruby
gem 'ruby-style-guide', :git => 'git@github.com:bulletproofnetworks/ruby-style-guide.git'
```

You will then need to update the **.rubocop.yml** so it inherits cops from the style guide. Add this to the beginning of the file.

```yaml
inherit_gem:
  ruby-style-guide: .rubocop.yml
```

###### NOTE
Inheritance from gems in rubocop requires a minimum of version **0.35**. When running *bundle install* ensure that the version of the rubocop gem is up to date.

Alternatively you can set this in the **Gemfile** like so...

```ruby
gem 'rubocop', '> 0.35'
```

Be sure to run a *bundle install* on the repo to cache the ruby-style-guide locally.

### Atom configuration
If you are using [github's Atom IDE](https://atom.io), on the fly linting can be configured by installing the [linter](https://atom.io/packages/linter) and [linter-rubocop](https://atom.io/packages/linter-rubocop)

```bash
gem install rubocop
apm install linter
apm install linter-rubocop
```

In *~/.atom/config.cson* specify the absolute path of your **rubocop** executable. For mac users that have a rbenv environment use the following to ensure the linter uses the appropriate executable for the ruby version currently in use.

```yaml
'linter-rubocop':
  'executablePath': /Users/[MYUSERNAME]/.rbenv/shims/rubocop
```
