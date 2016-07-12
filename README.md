# phppgadmin-authallowed

This image is based on [`maxexcloo/phppgadmin`](https://hub.docker.com/r/maxexcloo/phppgadmin/). This image is the same as the one it is built from, except that the `extra_login_security` is set to `false`, allowing users to login to manage databases.

## How to use
You can run using the command:
~~~bash
docker run --name="phppgadmin" --env=["VIRTUAL_HOST={Virtual Host}"] --link={Database Container Name}:postgresql -p {Port}:80 -d jeerbl/phppgadmin-authallowed
~~~
This will make the phppgadmin server run on `{Virtual Host}:{Port}`.

Make sure that the container running {Database Name} is on Docker's default bridge network
~~~bash
docker network connect bridge {Database Container Name}
~~~

The default login/password for PostgreSQL databases is postgres/postgres.
