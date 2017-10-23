# mageinferno-docker-magento2
Steps to setup development environment using Mage Inferno Magento 2 Docker Images.

Download, unzip to htdocs/
https://github.com/mageinferno/magento2-docker-compose

To avoid the issue of localhost not loading due to browsers (e.g. chrome) not saving cookies for URLs with less than 2 dots (.) in them depicted here: https://github.com/magento/magento2/issues/2614 || https://alankent.me/2015/04/25/use-of-localhost-when-installing-magento-2-quick-note/

Do this:
In the Magento setup environment variables: setup.env, change:
Magento base URL to: 192.168.99.100:8000

In CLI, cd into unzipped folder and do:
docker-compose run --rm setup

then:
docker-compose up -d

Magento CLI: docker-compose exec phpfpm ./bin/magento [magento command]

Magento admin URL: 
docker exec -it PHPCONTAINERID head -5 app/etc/env.php => This should give you the first 5 lines of app/etc/env.php, the 5th line being the admin url.

Official Documentation: https://github.com/mageinferno/magento2-docker-compose
