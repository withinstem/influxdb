# InfluxDB stem

InfluxDB is a time series database designed to handle high write and query loads.[\*](https://www.influxdata.com/products/influxdb-overview/)

## Build

Build from the official [influxdb](https://hub.docker.com/_/influxdb) docker image. Stick to current version.

## Configuration

Configuration based on the official [sample config](https://github.com/influxdata/influxdb/blob/1.7/etc/config.sample.toml).

Changes made:

* Usage data reporting disabled to minify risk of performance issues on isolated or high-latency external networks.
* Series and tags limits disabled to prevent issues with clients generating dynamic names like [Bucky](https://github.hubspot.com/bucky/) do.
* HTTP queries logging disabled to prevent disk space issues on rarely maintained servers.

## Deployment

Deploy with docker using embedded [ops-docker](https://github.com/ops-tools/ops-docker) tool.

Scripts available:

* `scripts/start` for launching local instance.
* `scripts/rollout` for rolling out to remote host
* `scripts/rollback` for rolling back

## License

[The Unlicense](LICENSE).
