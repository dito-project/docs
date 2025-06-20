# Usage

Start the server with the default configuration:

```bash
make run
```

Or directly:

```bash
./bin/dito -f /path/to/custom-config.yaml -enable-profiler
```

## Configuration File

- **Template:** `cmd/config.yaml`
- **Runtime:** `bin/config.yaml`

Example configuration:

```yaml
port: '8081'
hot_reload: true
metrics:
  enabled: true
  path: "/metrics"
logging:
  enabled: true
  verbose: false
  level: "info"
plugins:
  directory: "./plugins"
  public_key_path: "./ed25519_public.key"
  public_key_hash: "<SHA256_HASH>"
transport:
  http:
    idle_conn_timeout: 90s
    max_idle_conns: 1000
    max_idle_conns_per_host: 200
    max_conns_per_host: 0
    tls_handshake_timeout: 2s
    response_header_timeout: 2s
    expect_continue_timeout: 500ms
    disable_compression: false
    dial_timeout: 2s
    keep_alive: 30s
    force_http2: true
locations:
  - path: "^/test-ws$"
    target_url: "wss://echo.websocket.org"
    enable_websocket: true
    replace_path: true
  - path: "^/dito$"
    target_url: "https://httpbin.org/get"
    replace_path: true
    transport:
      http:
        disable_compression: true
    additional_headers:
      X-Custom: "true"
    excluded_headers:
      - Cookie
    middlewares:
      - hello-plugin
```
