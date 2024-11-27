# Docker local environment setup

Run `cp .env.example .env` to create a `.env` file

Add the following to your `/etc/hosts` file:

```bash
# Docker local environment
127.0.0.1       adminer.local
127.0.0.1       mailpit.local
127.0.0.1       minio.local
```

Run `docker-compose up -d` to start the containers

You can pass any files you want to run in the containers by adding them to the `./<service-folder>/bridge` folder

You can access the following services:
- Adminer: [http://adminer.local](http://adminer.local)
- MailPit: [http://mailpit.local](http://mailpit.local)
- MailPit: [http://minio.local](http://minio.local)
- MailPit SMTP: `localhost:1025`
- Postgres: `localhost:5432`
- Mysql: `localhost:3306`
- Redis: `localhost:6379`
- Minio: `localhost:9000`

You can also add the following aliases to your `.bashrc` or `.zshrc` file:

```bash
alias php='docker run --rm --network=local-environment_local-network -v $(pwd):/app -w /app -p 8000:8000 phpswoole/swoole:6.0-php8.4-alpine php'
alias go='docker run --rm --network=local-environment_local-network -v $(pwd):/app -w /app -p 8000:8000 golang:1.23.3 go'
```

and access php and go by running `php <file>` and `go run <file>` respectively.
You will be able to access databases in executed code as well.