# Docker Images for Laravel development

A docker-compose workflow for local Laravel development

## Install Laravel 9

1. Clone Laravel application

```sh
git clone -b 9.x https://github.com/laravel/laravel.git <project_name>
```

2. Copy `docker-compose.yml` file to your project root path

```sh
curl -o filename raw-link-to-file
```

3. From your project directory, start up your application by running

```sh
docker-compose up -d
```

4. Enter the container bash

```sh
docker-compose exec app bash
```

5. Enjoy the development

## Licence

This work is under [MIT](LICENCE) licence.