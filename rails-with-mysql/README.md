# Rails template with MySQL

## Versions

* Ruby 2.5.1
* Ruby on Rails 5.2.1
* MySQL 8.0.12

## Usage

### Create docker image

```bash
$ docker-compose build
```

### Create database

```bash
$ docker-compose run --rm web bundle exec rails db:create
```

### Run docker containers

```bash
$ docker-compose up -d
```

### Stop docker container

```bash
$ docker-compose stop
```