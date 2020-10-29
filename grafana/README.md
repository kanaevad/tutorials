# Running Grafana with docker-compose
## Get started

1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Run service
```
$ docker-compose up --build
```

- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- The Grafana documentation is available at [grafana.com/docs](https://grafana.com/docs/).

## License

Grafana is distributed under the [Apache 2.0 License](https://github.com/grafana/grafana/blob/master/LICENSE).