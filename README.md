## Docker Compose MySQL e Adminer

```sh
## Criando o docker-compose.yml
version: '3.1'

services:
  mysqlsrv:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: 'MySql@2021!'
      MYSQL_DATABASE: 'mysql_db'
    ports:
      - '3306:3306'
    networks:
      - mysql-compose-network

  adminer:
    image: adminer
    ports:
      - 8080:8080
    networks:
      - mysql-compose-network

networks:
  mysql-compose-network:
    driver: bridge
```

```sh
## Comando para executar docker-compose.yml
docker-compose -f docker-compose.yml up

## Outros comandos
docker-compose help
docker-compose build
docker-compose up
```

## Adminer

[LocalHost:8080](http://localhost:8080)

- Server: mysqlsrv
- User: root
- Password: MySql@2021!
- Database: mysql_db
