# Docker-Compose Configuration for Grafana

This `docker-compose.yml` file can be used to build a Grafana environment that also includes InfluxDB and Telegraf. I wrote [a more detailed post](https://nuntz.com/projects/building-dashboards-with-grafana/)  that explains the setup and contains sample configuration files.

Each container has one or more volumes defined for data persistency, in `./data/`:

* `./data/influxdb` for the InfluxDB data;
* `/data/telegraf/telegraf.conf` for the Telegraf configuration file;
* `./data/grafana/lib`, `./data/grafana/log`, and `/data/grafana/etc` for the Grafana data.

The current directory must contain a `data` directory, and two configuration must be created before running the containers:

* `./data/telegraf/telegraf.conf`, which defines the output and input plugins for Telegraf (you can use the default one);
* `./data/grafana/etc/grafana.ini` , which is used to configure Grafana (again, the `defaults.ini` file can be used as a template).
