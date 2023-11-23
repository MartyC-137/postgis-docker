# postgis-docker
A docker compose file containing PostGIS for `arm64` architecture and pgadmin4. This will allow you to create a PostgreSQL spatial database on a Silicon Mac and manage it with PGAdmin.

This project uses the following Docker base images:

- [x] [imresamu/postgis](https://hub.docker.com/r/imresamu/postgis)
- [x] [dpage/pgadmin4](https://hub.docker.com/r/dpage/pgadmin4)

## Getting started

- Clone the repo:
>
> ``` bash
> cd repo/location
> git clone https://github.com/MartyC-137/postgis-docker.git
> ```

- Create a directory in the root of the repo called `data`:
> 
> ``` bash
> mkdir data
> ```

- Create a file called `pgadmin_pwd.txt` containing your password. This file is ignored in this repo but make sure to run the following if you are working on your own:
>
> ``` bash
> echo "pgadmin_pwd.txt" >> .gitignore
> echo "data/" >> .gitignore
> ```
