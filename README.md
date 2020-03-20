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
9. `docker exec -it app bin/install`
10. `sudo chown -R ```whoami```:```whoami``` web/magento && echo "...almost done always..."`

## Setup XSD Paths

1. `docker exec -it app bin/magento dev:urn-catalog:generate ../misc.xml`
2. `chown ``whoami``:``whoami`` web/misc.xml`
3. `sed -i 's/\$PROJECT_DIR\$/\$PROJECT_DIR\$\/web\/magento/g' web/misc.xml`
2. `cp web/misc.xml .idea/misc.xml`
