this docker env follow [this tutorial](https://testdriven.io/blog/fastapi-docker-traefik/).


> ## Setup Enviroment

create `.env` file in the same directory as the `docker-compose.yaml` file. copy the variables from down below into the `.env` and change the values so they match to your need. 
```
POSTGRES_USER=<username>
POSTGRES_PASSWORD=<password>
POSTGRES_DB=<db_name>
POSTGRES_PORT=<postgres_port_number> (recommended 5432)
```

start with run: (use this command to show any new updates in the fast api container). without the `--env-file` tag, the `.env` file will not be recognized
```
docker-compose --env-file .env up -d --build
```

see api logs on (run on cmd in any location):
```
docker logs -f <CONTAINER ID>
```

>## Postgres Use
to write sql commands enter the postgres bash with:
```
docker-compose exec db psql --username=fastapi_traefik --dbname=fastapi_traefik
```
show list of databases:
```sql
\l 
```
connect to database:
```sql
\c fastapi_traefik
```


> ## Remove the Enviroment
take down the containers
```
docker-compose down
```
remove all images
```
docker system prune -a
```

check the volume created with 
```
docker volume ls
```
and delete the volume with 
```
docker volume rm <NAME_OF_VOLUME>
```

