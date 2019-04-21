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
$ docker-compose run web bundle exec rails new . --database=postgres --skip-bundle
```

### Update `/myapp/config/database.yml`

```yml
default: &default
  adapter: mysql2
  encoding: utf8
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password: password # set 'MYSQL_ROOT_PASSWORD' on docker-compose.yml
  host: db # set service name on docker-compose.yml
```

### Create database

```bash
$ docker-compose run --rm web bundle exec rails db:create
```

### Stop docker container

```bash
$ docker-compose stop
```

### Create docker image

```bash
$ docker-compose build
```
