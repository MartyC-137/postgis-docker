# PostGIS + PGAdmin in Docker for `arm64`

<div style="display: flex; justify-content: space-between;">
    <img src="assets/docker.jpg" alt="Docker" style="width: 50%;">
    <img src="assets/postgres.png" alt="Postgres" style="width: 50%;">
</div>

This repo contains a Docker configuration to run PostgreSQL, PostGIS and PGAdmin on the `arm64` architecture. This will allow you to create a PostgreSQL spatial database on a Silicon Mac and manage it with PGAdmin.

This project uses the following Docker base images:

- [imresamu/postgis](https://hub.docker.com/r/imresamu/postgis) - PostGIS + PostgreSQL
- [dpage/pgadmin4](https://hub.docker.com/r/dpage/pgadmin4) - PGAdmin

## Getting started

**Download [Docker Desktop](https://www.docker.com/products/docker-desktop/)** 

- Clone the repo:
  
``` sh
cd repo/path/here
git clone https://github.com/MartyC-137/postgis-docker.git
```

- Create a directory in the root of the repo called `data`:

``` sh
mkdir data
```

- Create a file called `pgadmin_pwd.txt` containing your PG Admin password:

``` sh
echo "my_pgadmin_password" > pgadmin_pwd.txt
```

- Create a file called `postgres_pwd.txt` containing the password for connecting to and admistering the Postgis database. Note this file is only read when initializing the Postgres database the first time the container is started with an empty data sub-directory. If you want to change the database password after the initial container build, it will require using the `ALTER USER` command in the psql shell.

``` sh
echo "my_postgres_password" > postgres_pwd.txt
```

- If you didn't clone the repo and are working on your own, run the following:
  
``` sh
echo "pgadmin_pwd.txt" >> .gitignore
echo "data/" >> .gitignore
```

The containers are now ready to start.

### Setting up the database

Run the following command in a terminal:

``` sh
docker compose up --no-start
docker compose start
```

- Open a web browser and navigate to `http://localhost:5050/browser/` to start PGAdmin
- Enter your PGAdmin email/username (default: pgadmin@pgadmin.org) and password (your password from `pgadmin_pwd.txt`)
- Create a server named `postgis`:

![PGAdmin1](/assets/pgadmin1.jpg)

On the Connection tab, enter the following info and click Save:

- `Host name/address`: postgis
- `Port`: 5432
- `Maintenance database`: postgres
- `Username`: postgres
- `Password`: the password from `postgres_pwd.txt`

![!PGAdmin2](/assets/pgadmin2.jpg)
