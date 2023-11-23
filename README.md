# postgis-docker
A docker compose file containing PostGIS for `arm64` architecture and pgadmin4. This will allow you to create a PostgreSQL spatial database on a Silicon Mac and manage it with PGAdmin.

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
echo "my_password" >> pgadmin_pwd.txt
```

- If you didn't clone the repo and are working on your own, run the following:
  
``` sh
echo "pgadmin_pwd.txt" >> .gitignore
echo "data/" >> .gitignore
```

The containers are now ready to start.

### Setting up the database

``` sh
docker compose up
```