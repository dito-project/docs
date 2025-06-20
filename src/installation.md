# Installation

Ensure you have **Go 1.21+** and `make` installed.

## Quick Start

```bash
# Clone repo
git clone https://github.com/andrearaponi/dito.git && cd dito

# One-command setup & start
make quick-start
```
This will build binaries, generate keys, sign plugins, update configuration and start the server.

## Step-by-Step

```bash
# 1. Clone repo
git clone https://github.com/andrearaponi/dito.git && cd dito

# 2. Setup (build, keys, plugins, config)
make setup

# 3. Start server
make run
```

## Makefile Commands

| Category | Command | Description |
|----------|---------|-------------|
| **Quick** | `quick-start` | Clean, setup everything and start |
|  | `setup` | Full development setup (build, keys, plugins, config) |
|  | `setup-prod` | Full production setup (persistent keys, prod config) |
|  | `run` | Start the Dito server |
|  | `fix-config` | Quick command to fix configuration after setup |
| **Build** | `build` | Build Dito binary only |
|  | `build-plugins` | Build all plugins |
|  | `build-plugin-signer` | Build plugin-signer tool |
| **Security** | `generate-keys` | Generate Ed25519 key pair for development |
|  | `generate-prod-keys` | Generate persistent Ed25519 key pair for production |
|  | `sign-plugins` | Sign all plugins with development keys |
|  | `sign-plugins-prod` | Sign all plugins with production keys |
|  | `update-config` | Update bin/config.yaml with development key paths/hashes |
|  | `update-prod-config` | Update bin/config-prod.yaml with production key paths/hashes |
|  | `update-k8s-config` | Create configs/config-prod-k8s.yaml for Kubernetes deployment |
| **OpenShift** | `deploy-ocp` | Complete OpenShift production deployment |
|  | `deploy-ocp-dev` | Quick development deployment to OpenShift |
|  | `status-ocp` | Check OpenShift deployment status |
|  | `logs-ocp` | View OpenShift deployment logs |
|  | `clean-ocp` | Clean up OpenShift resources |
| **Debug** | `debug-config` | Debug configuration issues |
|  | `help` | Show all commands |
| **Cleanup** | `clean` | Remove build artifacts |
|  | `clean-plugins` | Clean plugin binaries only |
| **Development** | `test` | Run tests |
|  | `vet` | Run go vet |
|  | `fmt` | Format code |
|  | `sonar` | Run SonarQube analysis |

## Manual Installation

1. **Build Dito**
   ```bash
   go build -o bin/dito ./cmd/dito/main.go
   ```
2. **Build plugin-signer**
   ```bash
   cd cmd/plugin-signer && go build -o ../../bin/plugin-signer . && cd ../..
   ```
3. **Generate keys**
   ```bash
   ./bin/plugin-signer generate-keys
   ```
4. **Build plugins**
   ```bash
   find plugins -mindepth 1 -maxdepth 1 -type d -exec sh -c 'cd "$1" && go build -buildmode=plugin -o "$(basename "$1").so"' sh {} \;
   ```
5. **Sign plugins**
   ```bash
   find plugins -name "*.so" -exec ./bin/plugin-signer sign {} \;
   ```
6. **Update configuration**
   Ensure `public_key_path` and `public_key_hash` in `config.yaml` are correct.
7. **Run Dito**
   ```bash
   ./bin/dito
   ```
