# Localhost MYSQL with docker

## Setup default users and password

- change default password in `.env`
- Replace `user` with desired non-root user

## Run

- `docker-compose up -d`

## Access mysql server(optional)

- `docker exec -it local_mysql mysql -u root -p`
- Enter the your root password defined in `.env`

by default the `user` can be login from any mysql client, with password defined in `.env`

## create another user 

create a new user and allow to access any db from anyhost

```sh
mysql> CREATE USER 'some_user'@'%' IDENTIFIED BY 'your_password';
Query OK, 0 rows affected (0.01 sec)

mysql> GRANT ALL PRIVILEGES ON * . * TO 'some_user'@'%';
Query OK, 0 rows affected (0.01 sec)

mysql> FLUSH PRIVILEGES;
Query OK, 0 rows affected (0.01 sec)

```
