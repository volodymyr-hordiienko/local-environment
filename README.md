# Docker local environment setup

Run `cp .env.example .env` to create a `.env` file

Add the following to your `/etc/hosts` file:
```
# Docker local environment
127.0.0.1       adminer.loc
```
Run `docker-compose up -d` to start the containers

You can pass any files you want to run in the containers by adding them to the `./<service-folder>/bridge` folder

You can access the following services:
- Adminer: [http://adminer.loc](http://adminer.loc)
- Postgres: `localhost:5432`
- Mysql: `localhost:3306`
- Redis: `localhost:6379`
