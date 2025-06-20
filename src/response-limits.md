# Response Limits

Dito allows configuring maximum response body sizes globally and per location.

## Global Limits

```yaml
response_limits:
  max_response_body_size: 100000 # 100KB default limit
```

## Per-Location Limits

```yaml
locations:
  - path: "^/api/small"
    target_url: "https://api.example.com"
    max_response_body_size: 1024
    disable_response_buffering: false
  - path: "^/api/large"
    target_url: "https://api.example.com"
    max_response_body_size: 52428800
    disable_response_buffering: true
```

### Features

- Automatic 413 status code when limits are exceeded
- JSON error responses with details
- Early detection using `Content-Length`
- Works with buffered and streaming responses
- Logging when limits are exceeded
- Limits can be updated via hot reload

### Error Format

```json
{
  "error": {
    "code": 413,
    "message": "Response body size exceeds limit",
    "details": {
      "limit_bytes": 90,
      "path": "/api/endpoint"
    }
  }
}
```

### Buffering Control

- `false` (default): responses buffered in memory
- `true`: responses streamed directly to the client
