# Project Structure

```text
dito/
├── cmd/                   # Entry points (main application & plugin-signer)
├── app/                   # Core application logic
├── config/                # Configuration loader & hot-reload
├── handlers/              # Request routing & proxy handlers
├── middlewares/           # Built-in middlewares (plugins can add more)
├── plugin/                # Plugin loading, signing, and verification
├── plugins/               # Plugin implementations
├── transport/             # HTTP transport configuration
├── websocket/             # WebSocket proxy support
├── writer/                # Response writers and buffering
├── metrics/               # Prometheus metrics
├── logging/               # Structured logging
├── deployments/           # Deployment configurations
│   ├── kubernetes/        # Basic Kubernetes deployments
│   ├── openshift/         # OpenShift production deployments
│   └── docker/            # Docker Compose for development
├── configs/               # Configuration files and templates
│   └── templates/         # Configuration templates
├── scripts/               # Deployment and utility scripts
├── bin/                   # Built binaries and runtime files
├── plugins/               # Example and community plugins
├── transport/             # HTTP transport customization
├── websockets/            # WebSocket support
├── writer/                # Custom response writers
├── logging/               # Logging utilities
└── metrics/               # Prometheus metrics collection
```
