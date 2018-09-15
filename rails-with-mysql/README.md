# Rails template with MySQL

## Versions

* Ruby 2.5.1
* Ruby on Rails 5.2.1
* MySQL 5.7

## Usage

### Create docker image

```bash
$ docker-compose build
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