# Magento 2 Docker Env

## Development Flow

1. `git clone git@github.com:sablesoft/docker-m2.git <project_name>`
2. `cd <project_name>`
3. `cp .env.dist .env`
4. `nano .env`
5. `composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition=2.3.4 web/magento`
6. `cp docker/install web/magento/bin`
7. `docker-compose up --build -d`
8. `sleep 60`
9. `docker exec -it app bin/install && chown -R nginx:nginx *`
10. `echo "...almost done always..."`
