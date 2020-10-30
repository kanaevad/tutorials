# Running Redash with docker-compose
## Get started

1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Initialize database data for Redash 

```
$ docker-compose run --rm server create_db
```

3. Run service
```
$ sudo docker-compose up --build
```

- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- Redash documentation is available at [redash.io/help](https://redash.io/help).

## License

BSD-2-Clause.
