# Task for Backend engineers

## Task description
1. Refactor the project to improve its architecture and make it more maintainable.
2. Add tests to the project.

## Project description

The project contains 
- Entities and their associations. 
- Login form and after successful login, you'll land on a page with some statistics.
- Edit profile form.


## Project setup
1. Run the project with the docker setup. (Thank you Kévin Dunglas https://github.com/dunglas)
2. Create the database with the following command: `docker-compose exec php bin/console doctrine:database:create`
3. Update the schema with the following command: `docker-compose exec php bin/console doctrine:schema:update --force`
4. Load the fixtures with the following command: `docker-compose exec php bin/console doctrine:fixtures:load`
5. Open the project in your browser: https://localhost
6. Login with the following credentials: `username: john@lingoda.com, password: 123123`


# Symfony Docker

A [Docker](https://www.docker.com/)-based installer and runtime for the [Symfony](https://symfony.com) web framework, with full [HTTP/2](https://symfony.com/doc/current/weblink.html), HTTP/3 and HTTPS support.

![CI](https://github.com/dunglas/symfony-docker/workflows/CI/badge.svg)

## Getting Started

1. If not already done, [install Docker Compose](https://docs.docker.com/compose/install/) (v2.10+)
2. Run `docker compose build --no-cache` to build fresh images
3. Run `docker compose up --pull --wait` to start the project
4. Open `https://localhost` in your favorite web browser and [accept the auto-generated TLS certificate](https://stackoverflow.com/a/15076602/1352334)
5. Run `docker compose down --remove-orphans` to stop the Docker containers.

## Features

* Production, development and CI ready
* [Installation of extra Docker Compose services](docs/extra-services.md) with Symfony Flex
* Automatic HTTPS (in dev and in prod!)
* HTTP/2, HTTP/3 and [Preload](https://symfony.com/doc/current/web_link.html) support
* Built-in [Mercure](https://symfony.com/doc/current/mercure.html) hub
* [Vulcain](https://vulcain.rocks) support
* Native [XDebug](docs/xdebug.md) integration
* Just 2 services (PHP FPM and Caddy server)
* Super-readable configuration

**Enjoy!**

## Docs

1. [Build options](docs/build.md)
2. [Using Symfony Docker with an existing project](docs/existing-project.md)
3. [Support for extra services](docs/extra-services.md)
4. [Deploying in production](docs/production.md)
5. [Debugging with Xdebug](docs/xdebug.md)
6. [TLS Certificates](docs/tls.md)
7. [Using a Makefile](docs/makefile.md)
8. [Troubleshooting](docs/troubleshooting.md)

## License

Symfony Docker is available under the MIT License.

## Credits

Created by [Kévin Dunglas](https://dunglas.fr), co-maintained by [Maxime Helias](https://twitter.com/maxhelias) and sponsored by [Les-Tilleuls.coop](https://les-tilleuls.coop).


Tests:
1. Login in to bash `docker compose exec php sh`
2. Create test database and load fixtures
    `php bin/console d:d:c --env=test`
    `php bin/console d:s:u --env=test --force`
    `php bin/console d:f:l --env=test --no-interaction`
3. Run tests `php bin/phpunit tests/`

TODO:
1. Join student and user - i know the context but i dont see the point of having two objects. 
2. If we assume that this is a complete application clean up could be done , removing not used methods etc. 