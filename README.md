# Docker Images for Laravel development

A docker-compose workflow for local Laravel development

## Install Laravel

1. Clone Laravel application

Laravel 9
```sh
git clone -b 9.x https://github.com/laravel/laravel.git <project_name>
```

Laravel 5.5
```sh
git clone -b 5.5 https://github.com/laravel/laravel.git <project_name>
```

2. Enter your project directory

```sh
cd <project_name>
```

3. Create .env file

```sh
cp .env.example .env
```

4. Add the following lines:

```
APP_URL=http://localhost:8080

...

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=<db_name>
DB_USERNAME=user
DB_PASSWORD=password
```

5. Copy `docker-compose.yml`

Laravel 9
```sh
curl -o docker-compose.yml https://raw.githubusercontent.com/fer-projekt/docker/main/laravel/9/docker-compose.yml
```

Laravel 5.5
```sh
curl -o docker-compose.yml https://raw.githubusercontent.com/fer-projekt/docker/main/laravel/5.5/docker-compose.yml
```

6. Start up your application by running

```sh
docker-compose up -d
```

7. Enter the container bash

```sh
docker-compose exec app bash
```

8. Install laravel and enjoy the development results on [localhost:8080](http://localhost:8080)

## Licence

This work is under [MIT](LICENCE) licence.
