# Plugin System

Dito uses Go plugins (`.so` files). Each plugin should be placed in its own subdirectory under `plugins/` and typically contains the compiled plugin (`<name>.so`), a signature file and an optional `config.yaml`.

## Signing & Verification

Plugin signing is mandatory and uses Ed25519 keys.

1. **Generate key pair**
   ```bash
   ./bin/plugin-signer generate-keys -privateKey ed25519_private.key -publicKey ed25519_public.key
   ```
2. **Compute public key hash**
   ```bash
   shasum -a 256 ed25519_public.key | awk '{print $1}'
   ```
3. **Update `config.yaml`** with the `public_key_path` and computed hash.
4. **Sign plugin**
   ```bash
   ./bin/plugin-signer sign -plugin path/to/plugin.so -privateKey path/to/ed25519_private.key
   ```

## Troubleshooting

- `public key integrity validation failed`: regenerate the hash and update the configuration.
- `failed to read public key`: verify the path and file permissions.
- `plugin signature verification failed`: re-sign with the correct key pair.
