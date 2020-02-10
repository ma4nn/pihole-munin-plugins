# MuninPiholePlugins
Munin plugins for monitoring Pi-hole (tested with Pi-hole v4.3 - https://pi-hole.net)

## Plugins
* `pihole_queries` show the queries rates (total dns queries and blocked queries/ads rates). The daily graph from this plugin should have a curve pace very similar to the one from the Pi-hole web interface.
* `pihole_cache` shows the queries cache rates (forwarded and cached queries rates)
* `pihole_clients` shows the unique clients statistics (counter which is reset every day).
* `pihole_querytypes` shows the percentage of DNS query types like A, AAAA, etc.

## Configuration

The Pi-hole web interface need to be installed in order to have the plugins working (they use the web interface api).

Sample setup for '/etc/munin/plugin-conf.d/munin-node':
```
[pihole_*]
user root
env.host 127.0.0.1
env.port 80
env.api /admin/api.php
env.pw secret
```
The password `env.pw` is only needed for `pihole_querytypes` and is the password of the Pi-hole web interface.

## Samples

### Graphs

**Queries graph in Pi-hole:**

![pihole](samples/pihole.png)

**Queries graph in Munin (daily):**

![pihole_queries-day](samples/pihole_queries-day.png)

**Queries graph in Munin (weekly):**

![pihole_queries-week](samples/pihole_queries-week.png)

**Cache graph in Munin (daily):**

![pihole_cache-day](samples/pihole_cache-day.png)

**Clients graph in Munin (weekly):**

![pihole_queries-week](samples/pihole_clients-week.png)

