# Database
Example database with some data for testing. This will be updated when scheemas are changed. Actual database should be created on each new server, and will be done . This is added as a submodule so it can be tested aginst the rest of the codebase.

## Settings
This database is designed to only be avaible inside a docker network, so securinty isnt important as on production, the ports of the database will not be exposed. The user name and password for acsessing it are `cosmic` and `cosmicUser` respectively.

## Docker-compose
This is built and hosted though My-sql and a docker compose file hosting just this, from its prent directory would sok like this.

```yml
version: "2"

services:
  db:
    image: mysql
    environment:
      - MYSQL_ROOT_PASSWORD=cosmicRoot
      - MYSQL_DATABASE=cosmic
      - MYSQL_USER=cosmic
      - MYSQL_PASSWORD=cosmicUser
    volumes:
      - ./db:/var/lib/mysql:rw
    ports: 
      - "3306:3306"
```