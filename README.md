## Collects and parses the logs created by PostgresSQL

When you run this module, it performs a few tasks under the hood:

- Sets the default paths to the log files (but don’t worry, you can override the defaults)
- Makes sure each multiline log event gets sent as a single event
- Uses ingest node to parse and process the log lines, shaping the data into a structure suitable for visualizing in Kibana
- Deploys dashboards for visualizing the log data

### Compatibility

The ```postgresql``` module was tested with logs from versions versions 9.5 on Ubuntu and 9.6 on Debian.


### Installation

### Linux:

<i>If you haven't already installed filebeat...</i>

1. Enter the following script into the console using elevated privileges

```
curl https://github.com/themarcusaurelius/vizion.ai/blob/master/beat-install-scripts/install-config-postgresql.sh > install-config-postgresql.sh; chmod a+x  install-config-postgresql.sh; ./install-config-postgresql.sh _PLACEHOLDER_API_ENDPOINT_
```

2. When prompted, select the proper environment to complete the installation.

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<i>If you have already installed filebeat...</i>

1. Enable the module.

```
filebeat modules enable postgresql
```

2. Restart Filebeat.

```
service filebeat restart
```

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

## Example Dashboard

This module comes with two sample dashboards.

The first dashboard is for regular logs.

![Imgur](https://imgur.com/JHX8xM4.png)

The second one shows the slowlogs of PostgreSQL.

![Imgur](https://imgur.com/c6almdx.png)
