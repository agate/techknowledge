# HOW TO PLAY

## Steps

1. `docker-compose up`
2. wait around 1 minute.
3. visit http://localhost:9090/graph?g0.range_input=1h&g0.expr=probe_success&g0.tab=0

## Key points

1. Prometheus only knows how to fetch "__Metrics__" page. But it doesn't know how to check things like if a http page's response is 2xx, 3xx or the page contains some text or send POST rather than GET.

2. Blackbox Exporter is kind of proxy. It can provide the metrics page for prometheus based on the config which user wrote. For example, user can use regex to match some text on the page's response and tell if this request is failed or not. More details you can read: https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md

    * In Blackbox Exporter's config. User needs to define some keys under the root `modules` section. So that you can use the module that you just defined in prometheus's config.