# discourse-username-localization

Localized username support.

This plugin is deprecated. Discourse Official supports unicode username since 2.3.0 beta9. Only the javascript part is valid for now, and will be deprecated soon.

In beta9+, set 'unicode username' to **true** and 'unicode username whitelist' to '**[\p{Han}\p{Katakana}\p{Hiragana}\p{Hangul}]**' will have the same effect.

## Install

### Docker

Add following code into `app.yml`:

```yaml
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - git clone https://github.com/discourse/docker_manager.git
          - git clone https://github.com/openSUSE-zh/discourse-username-localization.git
```          

### Vagrant

```
vagrant ssh

cd /vagrant

bundle exec rake plugin:install repo=http://github.com/openSUSE-zh/discourse-username-localization

bundle exec rake assets:clean

bundle exec rails s -b 0.0.0.0
```

## Update

### Vagrant

```
vagrant ssh

cd /vagrant

bundle exec rake plugin:update plugin=discourse-username-localization

bundle exec rake assets:clean

bundle exec rails s -b 0.0.0.0
```
