# docker-postgres-cn
docker postgres with zh-cn.UTF-8 locale

docker-compose sample

```
version: "3"
services:
  db:
    image: postgres-cn
    container_name: postgres
    restart: always
    volumes:
      - "./data:/var/lib/postgresql/data/pgdata"
    ports:
      - "5432:5432"
    environment:
      POSTGRES_DB: root
      POSTGRES_INITDB_ARGS: "-E UTF8 -k --locale=zh_CN.UTF8 --lc-messages=en_US.UTF8"
      POSTGRES_USER: root
      POSTGRES_PASSWORD: strongPassW@rd
      PGDATA: "/var/lib/postgresql/data/pgdata"
```