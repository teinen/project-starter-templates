# Rails template with PostgreSQL

## Versions

* Ruby 2.6.0
* Ruby on Rails 5.2.3
* PostgreSQL 10.5

## Usage

### Create docker image

```bash
$ docker-compose build
```

### Create rails app
```bash
$ docker-compose run --rm web bundle exec rails new . --force --database=postgresql --skip-bundle
```

### Update `/myapp/config/database.yml`

```yml
default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see Rails configuration guide
  # http://guides.rubyonrails.org/configuring.html#database-pooling
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  ### Add host, username, password ###
  host: db
  username: postgres
  password:
```

### Create database

```bash
$ docker-compose build
$ docker-compose run web bundle exec rails db:create
```

### Stop docker container

```bash
$ docker-compose stop
```
