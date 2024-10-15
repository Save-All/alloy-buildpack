# Grafana Alloy Buildpack for Heroku

This buildpack installs and configures Grafana Alloy for use with Heroku applications. Grafana Alloy is a lightweight agent that can collect metrics and logs from your application and send them to a Prometheus-compatible endpoint.

## Features

- Automatically installs Grafana Alloy on non-web dynos
- Configures Alloy to collect metrics from the application
- Sends metrics to a specified Prometheus endpoint

## Usage

To use this buildpack, add it to your Heroku application:

## Configuration

To configure the Grafana Alloy buildpack, you need to set the following environment variables:

1. `PROMETHEUS_PUSH_URL`: The URL of your Prometheus-compatible endpoint where metrics will be sent. Default: "https://localhost:9090/api/prom/push"
2. `ALLOY_USERNAME`: The username for basic authentication with the Prometheus endpoint.
3. `ALLOY_PASSWORD`: The password for basic authentication with the Prometheus endpoint.
4. `CELERY_METRICS_URL`: The URL where Celery metrics are exposed. Default: "localhost:8404"

You can set these environment variables using the Heroku CLI or through the Heroku dashboard:

```bash
heroku config:set PROMETHEUS_PUSH_URL="https://your-prometheus-endpoint/api/prom/push"
heroku config:set ALLOY_USERNAME="your-username"
heroku config:set ALLOY_PASSWORD="your-password"
heroku config:set CELERY_METRICS_URL="http://your-heroku-app.herokuapp.com/metrics"
```


