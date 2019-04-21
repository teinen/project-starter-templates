# Rails template with MySQL

## Versions

* Ruby 2.6.0
* Ruby on Rails 5.2.3
* MySQL 5.7

## Usage

### Create docker image

```bash
$ docker-compose build
```

### Create rails app
```bash
$ docker-compose run --rm web bundle exec rails new . --database=mysql --skip-bundle
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

### Run docker containers

```bash
$ docker-compose up -d
```

### Create database

```bash
$ docker-compose run --rm web bundle exec rails db:create
```

### Stop docker container

```bash
$ docker-compose stop
```