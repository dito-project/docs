# Features

- **Layer 7 Reverse Proxy:** Handles HTTP and HTTPS requests efficiently.
- **WebSockets Support:** Proxy WebSocket connections with ease.
- **Dynamic Configuration Reloading:** Update configurations without restarting the server.
- **Extensible Plugin System:** Enhance Dito with custom Go plugins for authentication, caching, rate limiting, request/response transformation, custom logging and more.
- **Plugin Security:** Plugins are signed with Ed25519 keys and verified at startup.
- **Custom TLS Certificate Management:** Support for mTLS and custom certificates for backend connections.
- **Header Manipulation:** Add or remove HTTP headers as needed.
- **Advanced Logging:** Asynchronous logging with customizable verbosity and performance optimizations.
- **Custom Transport Configuration:** Fine-tune HTTP transport settings per location or globally.
- **Response Body Size Limits:** Control maximum response body sizes globally and per location with proper error handling.
- **Response Buffering Control:** Enable or disable response buffering per location for optimal performance.
- **Prometheus Metrics:** Monitor performance and behavior with detailed metrics.
