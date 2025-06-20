# Containerization & OpenShift Deployment

Dito is containerized and optimized for OpenShift.

## Quick Deployment

```bash
chmod +x scripts/deploy-ocp.sh
./scripts/deploy-ocp.sh
```

Custom namespace and version:

```bash
./scripts/deploy-ocp.sh -n my-dito -v latest
```

Other options include force key regeneration (`-f`), configuration only (`-c`) or deploy only (`-d`).

## Manual Deployment Steps

### 1. Build and Push Container Image

```bash
./docker-build.sh
```

### 2. Generate Production Keys

```bash
make generate-prod-keys
```

### 3. Create OpenShift Resources

```bash
oc new-project dito
oc create secret generic dito-keys \
    --from-file=ed25519_public.key=bin/ed25519_public_prod.key \
    --from-file=ed25519_private.key=bin/ed25519_private_prod.key

HASH=$(shasum -a 256 bin/ed25519_public_prod.key | awk '{print $1}')
sed "s/PLACEHOLDER_HASH_TO_BE_REPLACED/$HASH/" configs/templates/application.yaml > configs/config-prod-k8s.yaml

oc create configmap dito-config \
    --from-file=config.yaml=configs/config-prod-k8s.yaml
```

### 4. Deploy Application

```bash
oc apply -f deployments/openshift/production-deployment.yaml
```

### Deployment Models

| File | Use Case | Features |
|------|----------|----------|
| `deployments/kubernetes/basic-deployment.yaml` | Basic deployment | Simple setup |
| `deployments/openshift/production-deployment.yaml` | Production deployment | Plugin signing, proper secrets, health checks |

### Security Features

#### Container Security
- Non-root execution (user ID 1001)
- Read-only root filesystem
- Dropped capabilities
- OpenShift security contexts

#### Key Management
- External key generation
- Runtime plugin signing
- Secure secret mounting
- Proper file permissions

### Configuration Management

Dito supports template-based configs, environment-specific configs and hot reload via ConfigMaps. See `configs/README.md` for details.
