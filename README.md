# Docker Images for Laravel development

A docker-compose workflow for local Laravel development

## Install Laravel

1. Clone Laravel application

Laravel 9
```sh
git clone -b 9.x https://github.com/laravel/laravel.git <project_name>
```

Laravel 6
```sh
git clone -b 6.x https://github.com/laravel/laravel.git <project_name>
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
DB_DATABASE=database
DB_USERNAME=user
DB_PASSWORD=password
```

5. Copy `docker-compose.yml`

Laravel 9
```sh
curl -o docker-compose.yml https://raw.githubusercontent.com/fer-projekt/docker/main/laravel/9/docker-compose.yml
```

Laravel 6
```sh
curl -o docker-compose.yml https://raw.githubusercontent.com/fer-projekt/docker/main/laravel/6/docker-compose.yml
```

Laravel 5.5
```sh
curl -o docker-compose.yml https://raw.githubusercontent.com/fer-projekt/docker/main/laravel/5.5/docker-compose.yml
```

6. Start up your application by running

```sh
docker-compose up -d server
```

7. Install Laravel

```sh
docker-compose run --rm composer update
docker-compose run --rm artisan key:generate
```

8. Compiling Assets

This configuration should be able to compile assets with both laravel mix and vite. In order to get started, you first need to add  --host 0.0.0.0 after the end of your relevant dev command in package.json. So for example, with a Laravel project using Vite, you should see:

```sh
"scripts": {
  "dev": "vite --host 0.0.0.0",
  "build": "vite build"
},
```

Then, run the following commands to install your dependencies and start the dev server:

```sh
docker-compose run --rm npm install
docker-compose run --rm --service-ports npm run dev
```

After that, you should be able to use @vite directives to enable hot-module reloading on your local Laravel application.

Want to build for production? Simply run:

```sh
docker-compose run --rm npm run build
```

9. Enjoy the development results on [localhost:8080](http://localhost:8080)

## Licence

This work is under [MIT](LICENCE) licence.
