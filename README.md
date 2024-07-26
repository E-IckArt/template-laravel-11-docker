# template-laravel-11-docker
A reusable template based on laravel 11 - Docker ready

It's includes a PostgreSQL database and a PGAdmin 4 GUI.
It can be used as a back-end API or with Laravel blade template or any other tool you need.

A devContainer is already installed.

This application is ready to communicate with a front-end hosted on `localhost:3000`.

## Requirements

- PHP ^8.2
- Docker desktop

## Dependencies

| **composer.json** | **package.json*** | 
| -------- | -------- | 
| - laravel sanctum 4.0     |     | 
| - laravel tinker 2.9     |     | 
| _Dev dependencies_   |  _Dev dependencies_  | 
| - fakerphpbfaker 1.23    | axios 1.6.4     | 
| - laravel pint 1.13     | laravel-vite-plugin 1     | 
| - laravel sail 1.26     | vite 5.0     | 
| - laravel telescope 5.1     |      | 
| - mockery 1.6     |      | 
|- nunomaduro collision 8.0    |      | 
| - phpunit 11.0.1    |      | 

*Javascript dependencies are all installed by default using the sail command to build the laravel application.  
Maybe you don't need them.  

## Configuration

1 - Copy `.env.example` 
```shell
cp .env.example .env
```

2 - Update `.env`, `devcontainer.json` and `docker-compose.yml` file with your own configuration.  
Be careful with the names you give, they must be the same from one file to another.
💡 Use the find and replace function of your editor.

```shell
cp .env.example .env
```

3 - Create an alias for the sail command

```shell
alias sail='sh $([ -f sail ] && echo sail || echo vendor/bin/sail)'
```

4 - Run Docker

```shell
sail up -d 
```

5 - Install project's dependencies

```shell
sail composer install
```

If generate user interface from the back-end and need hot reload during devlopmment : 

```shell
sail npm install
```

6 - Run Migration

```shell
sail artisan migrate
```

7 - Open a browser and if you didn't change this ports :   
-  see your application at [http://localhost:8000](http://localhost:8000/)  
-  see your pgAdmin GUI at [http://localhost:5055/browser](http://localhost:5055/browser)  



