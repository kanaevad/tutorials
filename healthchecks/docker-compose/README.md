# Running Healthchecks with docker-compose
## Get started

1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Copy ```.env.example``` file to ```.env```
```
$ cp .env.example .env
```
3. Configure your ```.env``` file

| Parameter       | Function |
| ------------- |:-------------:|
| PUID=1000      | for UserID - see below for explanation |
| PGID=1000      | for UserID - for GroupID - see below for explanation |
| SITE_ROOT=<SITE_ROOT> | The site's top-level URL (e.g., https://healthchecks.example.com) |
| DEFAULT_FROM_EMAIL=<DEFAULT_FROM_EMAIL> | From email for alerts |
| EMAIL_HOST=<EMAIL_HOST> | SMTP host |
| EMAIL_PORT=<EMAIL_PORT> | SMTP port |
| EMAIL_HOST_USER=<EMAIL_HOST_USER> | SMTP user |
| EMAIL_HOST_PASSWORD=<EMAIL_HOST_PASSWORD> | SMTP password |
| EMAIL_USE_TLS=<True or False> | Use TLS for SMTP (True or False) |
| ALLOWED_HOSTS=<ALLOWED_HOSTS> | array of valid hostnames for the server ["test.com","test2.com"] or "*" |
| SUPERUSER_EMAIL=<SUPERUSER_EMAIL> | Superuser email |
| SUPERUSER_PASSWORD=<SUPERUSER_PASSWORD> | Superuser password |

When using volumes (-v flags) permissions issues can arise between the host OS and the container, we avoid this issue by allowing you to specify the user ```PUID``` and group ```PGID```.

Ensure any volume directories on the host are owned by the same user you specify and any permissions issues will vanish like magic.

In this instance ```PUID=1000``` and ```PGID=1000```, to find yours use id user as below:

```
$ id username
    uid=1000(dockeruser) gid=1000(dockergroup) groups=1000(dockergroup)
```

4. Run service
```
$ docker-compose up --build
```

- Port redirection `-p` is necessary to allow healtcheck pings from local netwotk.
- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- Healthchecks documentation is available at [healthchecks.io/docs/](https://healthchecks.io/docs/).

## License

BSD-3-Clause License
