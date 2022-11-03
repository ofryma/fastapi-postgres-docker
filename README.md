this docker env follow [this tutorial](https://testdriven.io/blog/fastapi-docker-traefik/).



start with run: (use this command to show any new updates in the fast api container) 
```
docker-compose up -d --build
```

see api logs on:
```
docker logs -f <CONTAINER ID>
```

### Postgres Use
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


