# Regolith Documentation
### Documentation for the Harvest API

## Startup Orders for Regolith Docker Container
The regolith docker container needs to be run matching port 80:80

On startup, the Regolith Docker Container needs to do the following:
- cd to the /api folder
- run composer install
- start nginx
- start php7.0-fpm

