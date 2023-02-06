# Bootstrap-popeye

# STEP 0 : HELLO DOCKER

1. Find the official PostgreSQL image and import it on your machine.

```bash
docker pull postgres
```

2. Show how many images you have on your machine.

```bash
docker image ls -all
or
docker images
```

3. Run a PostgreSQL container.

```bash
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```

4. Show containers running on your machine. Do you see the container ID of PostgreSQL?

```bash
docker ps
```
Yes !

5. Is your previous PostgreSQL container still running? Fine, stop it

```bash
docker stop id 
```

6. Even if your container is stopped, it still exists on your system. Remove it.

list all containers: ```docker container ls -a```
```bash
docker rm id
```


7. Oh no, the developper told you that their application is only compatible with PostgreSQL 9.4. Run a
container with this specific version.
```bash
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres:9.4

```

8. You want to list tables, but you cannot connect to this PostgreSQL instance from your host. It seems
like the needed port is not exposed on your machine. How to fix that?

```bash

```
9. In the official PostgreSQL image, the default username/password/database are: postgres/postgres
/postgres. This is uncreative, but above all unsecure! Find how to change PostgreSQL’s password (when
executing docker run).

```bash
docker run -it -e POSTGRES_PASSWORD=some_password postgres:9.4
```
10. At the moment, data is not persistant and vanish from hard drive when its associated container is
removed. Be kind to your data and offer them a place to stay on your hard drive.

```bash
-v /path/on/host:/path/in/container
```
11. Can you find out which day it is in the container? Execute the command date into a running PostgreSQL container

```bash
docker exec -it some-postgres  psql -U postgres
select current_time at time zone 'brt';
```
12. Because you absolutely love reading lines of information written on your screen, find how to display
the logs of your container. (Bonus point if you find how to display them in real time.)
```bash
docker logs -f mypostgres94
```
# STEP 1: TIME TO CRAFT

# STEP 2: TIME TO CRAFT THE CRAFTER
