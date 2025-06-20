# Metrics

Dito exposes Prometheus metrics to monitor performance and behaviour.

## Available Metrics

- `http_requests_total` – total number of HTTP requests processed
- `http_request_duration_seconds` – duration histogram
- `active_connections` – number of active connections
- `data_transferred_bytes_total` – bytes transferred
- Standard Go runtime and promhttp metrics

## Configuration

Enable metrics in `config.yaml`:

```yaml
metrics:
   enabled: true
   path: "/metrics"
```
