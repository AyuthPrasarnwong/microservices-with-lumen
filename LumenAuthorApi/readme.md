Get Started
-----------

#### Requirements

To run this application on your machine, you need at least:

* docker

Run the docker for development:
---------------------
First you need to copy `.env.example` to `.env` for setup environment of appplication

To start the application and run the containers in the background, use following command inside project root:

```bash
docker-compose up -d
```

To stop all containers, use following command inside project root:

```bash
docker-compose down
```

Installing Dependencies via Composer
------------------------------------
Run the composer installer:

```bash
docker exec -it author-ms-app composer install
```
or
```bash
docker exec -it author-ms-app composer update
```

Database Setup
------------------------------------
Run the migration artisan command:
```bash
docker exec -it author-ms-db bash  
mysql -u root -p
GRANT ALL ON laravel.* TO 'homestead'@'%' IDENTIFIED BY 'secret';
FLUSH PRIVILEGES;
EXIT;
docker exec -it author-ms-app php artisan migrate:refresh --seed
```

Map the domain
------------------------------------
Open the hosts file on your local machine `/etc/hosts`.
```bash
127.0.0.1  api-author.lumen.loc
```

Running Application
------------------------------------
Open the browser
```bash
http://api-author.lumen.loc:8066
```