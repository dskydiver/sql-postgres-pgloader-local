## Postgres & Mysql & pgloader

1. Run the containers.

```bash
docker-compose up -d
```

- Then clone dump mysql data to mysql container using any UI tool (like DBeaver).

2. Copy loadfile to pgloader container.

```bash
docker cp loadfile.load <pgloader container id>:/load_file.load
```

- To see the pgloader container id.

```bash
docker ps
```

3. Migrate with pgloader.

```bash
docker-compose exec pgloader pgloader ./load_file.load
```
