# Symfony-docker
This project contains a ready to run Docker configuration for Symfony-based projects, preparing containers for MySQL, PHP and Nginx.

## Requirements
[Download](https://docs.docker.com/get-docker/) and install Docker for your OS. After installation process, check if it has installed properly by typing in terminal
```bash
docker -v
```
and
```bash
docker-compose -v
```

## Installation
1. Open terminal in project directory and type
  ```bash
  docker-compose up -d --build
  ```
2. After build, run interactive bash inside PHP container
```bash
docker exec -i {your_php_container_name} bash
```
3. Configure git inside the container
```bash
git config --global user.name "{your_username}"
git config --global user.email "{your_email}"
```
4. Install Symfony inside the container
```bash
curl -sS https://get.symfony.com/cli/installer | bash
mv /root/.symfony/bin/symfony /usr/local/bin/symfony
```
5. Create new Symfony project inside the container
```bash
symfony new symfony --dir=/var/www/symfony
```
6. Type and go to this page in browser
```
localhost
```
7. If you are seeing Symfony welcome page, congratulations! Everything is done :)

## Database
Database is created inside container automatically. If you want to change its parameters (for example root password), then go to the `.env` file in root directory and change variable value.
