# mageinferno-docker-magento2
Steps to setup development environment using Mage Inferno Magento 2 Docker Images.

Download, unzip to htdocs/
https://github.com/mageinferno/magento2-docker-compose

In CLI, cd into unzipped folder and do:
docker-compose run --rm setup

then:
docker-compose up -d

Add to hosts file:
127.0.0.1 m2.localhost

Magento setup environment variables: setup.env
Magento base URL: m2.localhost:8000
Magento CLI: docker-compose exec phpfpm ./bin/magento [magento command]
Magento admin URL: docker exec -it PHPCONTAINERID head -5 app/etc/env.php => This should give you the first 5 lines of app/etc/env.php, the 5th line being the admin url.

Official Documentation: https://github.com/mageinferno/magento2-docker-compose
