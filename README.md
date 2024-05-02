<h2> Project _ Introduction </h2>

<p> 
Project Overview: Laravel-PHP Dockerized Application

This project aims to containerize a Laravel-PHP application for streamlined development and deployment. By leveraging Docker, the application's components are isolated into separate containers, facilitating scalability, portability, and ease of management.

1. **Application Components**:
   - **Source Code**: The Laravel-PHP application's source code resides on the host machine. This includes all PHP files, configuration files, views, controllers, and other necessary files.
   - **PHP Interpreter Container**: A dedicated container hosts the PHP interpreter, which executes PHP code in response to incoming requests from clients. This container is equipped with built-in PHP dependencies required for the application.
   - **NGINX Web Server Container**: Another container runs an NGINX web server responsible for handling incoming HTTP requests. It communicates with the PHP interpreter container to process PHP code and generate responses for clients. NGINX efficiently handles multiple requests, improving the application's performance.
   - **MySQL Database Container**: A separate container hosts a MySQL database for storing and retrieving data used by the Laravel application. This container ensures data persistence and separation from other components.
  
2. **Container Interaction**:
   - The NGINX server forwards incoming requests to the PHP interpreter container for processing PHP code. Once processed, the PHP interpreter generates responses, which are then returned to clients through NGINX.
   - The PHP interpreter interacts with the MySQL database container to perform database operations such as storing and retrieving data. This interaction ensures seamless data management within the application.

3. **Utility Containers**:
   - Utility containers are used to install dependencies required for the Laravel application. This includes Composer for managing PHP dependencies and NPM for managing JavaScript dependencies. These containers streamline the development process by automating dependency installation and ensuring consistency across environments.
   - Laravel Artisan, the command-line interface (CLI) for Laravel, is utilized within utility containers to execute tasks such as running database migrations. This ensures efficient management of database schema changes and data migrations.

4. **Docker Compose Integration**:
   - Docker Compose is utilized to orchestrate and manage the application's containers. The `docker-compose.yml` file defines the services, dependencies, and configuration for each container. It enables easy scaling, deployment, and management of the entire application stack.

5. **Development Workflow**:
   - Developers can work on the Laravel application locally on their host machines, leveraging Docker containers for a consistent development environment.
   - The use of utility containers simplifies dependency management and task execution, enhancing the development workflow.
   - Once development is complete, the application can be deployed to production environments with minimal configuration changes, thanks to the containerized architecture.

Overall, this Dockerized Laravel-PHP application offers a modular, efficient, and scalable solution for building and deploying web applications, streamlining development workflows and enhancing application reliability and performance.

</p>
<h3>Architecture</h3>

![architecture](https://github.com/Hemanthbugata/Laravel_PHP-dockerized-application/assets/102855092/7bee9497-a2ad-4416-9e77-5795db3b897c)

<h3>Execution with docker commands </h3>

   docker-compose run --rm composer create-project --prefer-dist laravel/laravel (creates project in src and installs dependencies of server , php and mysql with composer (utility container)

   docker-compose up -d server php mysql ( create images for sever php mysql and laravel project , then start containers , localhost:8000:80 displays the application )

   docker-compose down ( stopping / dropping the containers)

   docker-compose run --rm  artisan migrate (checks the connectivity of database)


   docker images (shows all docker images )

   docker ps -a (shows all containers)
   

