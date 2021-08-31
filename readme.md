#### APROJECT v1 Building microservice achiko website

``````
Created by budi santoso ( Development Operations )
Contact us and maintainer budi.s@achiko.co
date last update and commit 19 Januari 2020
``````
- This docker running by docker-compose.yml to build service mysql, php, nginx, with workspace wordpress.
- Use .env to build username, password, database and latest version mariadb. Following .env-example to configure username, password, database mariadb.
- You can adding wordpress project on workspace, create workspace domain name and copy paste project wordpress to folder workspace.
- This application running by php7.3-fpm, mysql latest, and nginx latest on container.
- You can edit local.ini to update config php.ini.
- Build ssl / https secure connection by certbot and automacally renewal certificates. Following note to build your certificates end to end encryption.

### Command pada docker
- docker-compose up -d --build                                                   : to build container by docker-compose.yml
- docker-compose down                                                            : to shutdown container and network docker-compose already running in folder docker config.
- docker-compose restart docker_service_name                                     : to restart container docker.
- docker system prune --all                                                      : to remove all cache image, network, and container which has been deactivated in docker.
- docker volume prune                                                            : to remove volume which has been deactivated in docker.
- docker-compose up -d --force-recreate --no-deps --build docker_service_name    : for recreate and rebuild container docker.
- docker exec -it --user root container_name bash                                : for exec user root to enter the system container name in docker.
- docker-compose stop                                                            : to stop all service container docker.
- docker-compose logs docker_service_name                                        : see logs service container in docker-compose.
- docker-compose rm docker_service_name                                          : remove container already shutdown in docker.

> *NOTE: To use your existing web server, make sure it is running and listening on port 80 before executing the following command, certbot certonly --webroot
You will be prompted to enter, among other information, your domain name(s) and the path to your webroot, which is `/var/www/` by default on most Linux systems. Alternatively, you may specify the required information as command arguments. For example: 
certbot certonly --webroot --webroot-path /var/www/ --agree-tos -m your_email@example.com -d www.example.com -d example.com
Using the standalone web server in order to use the standalone server, first ensure the availability of port 80. You can check for any processes binding to that port using: 
ss -lntp 'sport = 80'
If needed, stop the offending service/process before proceeding. Then, issue the command: 
certbot certonly --standalone
Once the certificate is issued, you will need to configure your web server manually. The relevant files can be found in /etc/letsencrypt/live/your_domain or $PATH/docker-config/nginx/ssl.*


> *NOTE: Following step in readme.md* 

#### Thank you and wish you happy :)
