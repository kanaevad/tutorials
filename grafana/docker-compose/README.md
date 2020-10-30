# Running Grafana with docker-compose
## Get started

1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Create directory for Grafana data 

```
$ mkdir data
```

3. Grafana runs as the grafana user (UID: 472) in the grafana group (GID: 472) in the container. You must ensure that all files are readable, and where necessary (e.g. the working/session directory) writeable for this user on the host machine. For example:

```
$ sudo chown -R 472:472 data/
```

4. Run service
```
$ docker-compose up --build
```

- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- The Grafana documentation is available at [grafana.com/docs](https://grafana.com/docs/).

## License

Grafana is distributed under the [Apache 2.0 License](https://github.com/grafana/grafana/blob/master/LICENSE).