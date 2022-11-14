# php-docker-starter
Reference: https://www.digitalocean.com/community/tutorials/how-to-bootstrap-a-new-laravel-application-with-docker-compose

Add the environment variables to your `.bashrc` or `.zshrc` file.
```
export USER=$(whoami)
export UID=$(id -u)
export GID=$(id -g)
```

Copy the `.env.example` to .`env` and set the environment variables.

```
cp .env.example .env
```

.env file

```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_NAME=
DB_USERNAME=
DB_PASSWORD=
```

### Bootstrap a Laravel application
```
docker-compose exec app composer create-project laravel/laravel --prefer-dist application
docker-compose down
```

Update the volumes in the app and nginx service.

docker-compose.yml
```
  volumes:
    - ./application/:/var/www
```

```
docker-compose up -d
```
