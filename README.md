# Overview

Learn Laravel.

## Usage

The development environment is defined in `docker-compose.yml`.
It is developed using the Remote container feature of Visual Studio Code.

### Install libraries

For development:

```bash
$ composer install
```

For production:

```bash
$ composer install --no-dev
```

### Connect Database

```bash
$ docker exec learn-laravel-mysql bash -c 'mysql -u $MYSQL_USER -p$MYSQL_PASSWORD $MYSQL_DATABASE'
```
