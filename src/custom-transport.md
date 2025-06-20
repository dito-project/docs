# Custom Transport Configuration

Customize how Dito connects to backend services.

- **Timeouts and Connection Limits**: adjust to match backend behavior.
- **TLS Settings**: manage handshake timeouts and enforce HTTP/2 if needed.
- **Custom Certificates**: specify client certificates for mTLS backends.

## WebSocket Support

Add `enable_websocket: true` to a location to proxy WebSocket connections.

```yaml
locations:
  - path: "^/test-ws$"
    target_url: "wss://echo.websocket.org"
    enable_websocket: true
    replace_path: true
```

### Upcoming Enhancements

Future versions will provide enhanced TLS control, improved error handling and detailed metrics for WebSocket traffic.

## TLS/SSL

Support for mTLS is built in. Specify `cert_file`, `key_file` and `ca_file` to secure backend connections.
