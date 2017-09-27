## Laravel-Docker

A basic and common docker structure to run Php projects with **composer, nginx, redis** and **queues**



To get started just add *docker-compose.yml*  to your root path and run 

```docker-compose up -d```



The follow paths will be created in your project:

* vendor

* composer-cache

* db-data

* redis-data

  ​
  
Make sure to ignore its contents in your *.gitignore* file



#### Running Commands

To run commands like *composer install*  you should refer the container name with *docker-compose exec* command: ```docker-compose exec php composer install``` or ```docker-compose exec php composer update``` 

#### Running Artisan Commands
To run artisan commands, you should call php named container with *docker-compose*:
```docker-compose exec php php artisan migrate```  
and
```docker-compose exec php php artisan make:migration migration_name```

#### Running Redis Commands

To run Redis commands, you should follow the same: ```docker-compose exec redis redis-cli```



#### Running MySql Commands

To run MySql commands, you should follow the same, i.g: ```docker-compose exec mysql mysql -u root -p{password}```



#### Queue proccessment

The queue container was created with *restart always* option, it allow you to scale it individually, setting how many containers (workers) you want to proccess your queue
