# docker_mahara

## Requirements

- Docker
- Docker-compose

## Usage

1. Clone this repository

```
git clone git@github.com:kenneth-hendricks/docker_moodle.git docker_mahara
```
2. Find which version you need and checkout that branch
```
e.g. Mahara-1804-pgsql
```
3. Clone Moodle code into siteroot

```
cd docker_mahara
git@github.com:MaharaProject/mahara.git siteroot
```

4. Copy site config across

```
cp mahara-config siteroot/htdocs/config.php
```

5. Start containers

```
docker-compose up
```

## Utility Commands

Use the following command to enter the bash shell of each container.
Replaces using the docker exec function.

To change container names, change name in yaml file and control file.

Enter web container:

```
./control web
```

Enter db container:

```
./control db
```

Enter test database container:

```
./control testdb
```

## Running Tests

To setup the testing environment run:

```
./control web
composer install
php admin/tool/phpunit/cli/init.php
```

To run tests:

```
./control web
./vendor/bin/phpunit
```
