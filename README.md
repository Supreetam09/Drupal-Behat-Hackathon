# Drupal-Behat-Hackathon
This repository contains basic configuration files to setup and run Behat in a fresh Drupal 9 site

## Steps to set up Behat in Drupal
- Copy `.lando.yml` file from [URL]() and paste in project root,
  - Update value of `config.webroot` key to `web` or `docroot` according to your application in `.lando.yml`
  - Update value of keys `creds.user` and `creds.password` according to your DB creds in `.lando.yml`


- Run `lando rebuild -y`


- Run `lando composer require acquia/blt-behat:dev-master -W`


- Run `lando composer require emuse/behat-html-formatter`


- Copy `blt.yml` file from [URL]() and paste inside `blt` folder,
  - Update value of `docroot` key to `web` or `docroot` according to your application in `blt.yml`


- Run `lando blt recipes:behat:init`


- Copy `behat.yml` file from [URL]() and `example.local.yml` file from [URL]() and paste inside `tests/behat` folder


- Run `lando blt tests:behat:init`

## Write and execute Behat
- Execute Behat tests by running `lando blt tests:behat`


- You can override Behat configuration while executing using `-D` option. E.g. `lando blt tests:behat -D behat.tags=@example`

- Look for existing Behat steps by running `lando blt tests:behat:list:definitions`


- You can also execute by running `/app/vendor/bin/behat --config /app/tests/behat/local.yml --profile local` from inside Lando server