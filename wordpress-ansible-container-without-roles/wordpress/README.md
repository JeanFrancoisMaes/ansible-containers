# Wordpress

- A Wordpress-Mariadb example built from scratch on Centos 7.
- Creates a Mariadb container and a Wordpress container.


main.yml:

```
-  hosts: db
   vars:
     - wp_mysql_db: wordpress
     - wp_mysql_user: wordpress
     - wp_mysql_password: password
```
```
-  hosts: wordpress
   vars:
     - wp_mysql_db: wordpress
     - wp_mysql_user: wordpress
     - wp_mysql_password: password

```
We can change the user and database by editing the main.yml file.

main.yml
```
-  hosts: db
   vars:
     - wp_mysql_db: < database name >
     - wp_mysql_user: < user name >
     - wp_mysql_password: < password >
```

```
-  hosts: wordpress
   vars:
     - wp_mysql_db: < database name >
     - wp_mysql_user: < user name >
     - wp_mysql_password: < password >
```

Build Images.
-----------------
```
$ cd wordpress
$ ansible-container build
```

## Run the Container.

```
$ ansible-container run

```

## (optional) Push images to cloud.

```
$ docker login
$ ansible-container push

```
