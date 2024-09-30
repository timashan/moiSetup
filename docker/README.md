# Docker

[docker hub](https://hub.docker.com)

```bash
docker compose up
docker compose -f <yml> up
docker compose down
```

## Postrgress

docker-compose.yml

```bash
services:
  db:
    image: postgres:16
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: postgres
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data

volumes:
  postgres-data:
```
