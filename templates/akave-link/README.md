# Akave Link – Confidential Storage API Template

A production-ready template to deploy Akave decentralized storage API on Phala Cloud’s TEE with:
- Express REST API + Interactive Web UI
- Built-in akavecli binary (bundled in image)
- Password-gated API (optional)
- Wallet connect/disconnect at runtime (no secrets persisted)

## Deploy with Phala CLI

Prereqs
- Phala CLI installed: `npm i -g @phala/cli`
- Phala account + API key (`phala auth login`)
- Akave private key (funded on network)

Steps
```bash
# In this folder
cp .env.example .env
# Edit .env with your values (NODE_ADDRESS, PRIVATE_KEY, optionally ADMIN_PASSWORD_HASH)

# Deploy
phala cvms create \
  --name akave-link \
  --compose ./docker-compose.yml \
  --env-file ./.env \
  --vcpu 2 \
  --memory 2048 \
  --disk-size 20
```

Once created, open your deployment’s URL from the Phala dashboard.
- Health: `https://<appId>-80.<gateway-domain>/health`
- UI: `https://<appId>-80.<gateway-domain>/`

## Preflight (Phala/DStack)
- .env: set `PORT=80`
- docker-compose.yml: ensure `ports: ["80:80"]` and environment is a mapping
- Multi-arch image (linux/amd64) if you rebuild your own image
- CVM name ≤ 20 chars
- If base URL returns empty reply, use the `-80` form: `https://<appId>-80.<gateway>/health`

## Environment Variables (.env)
- NODE_ADDRESS (required) – e.g., `connect.akave.ai:5500`
- PRIVATE_KEY (required) – Ethereum private key for Akave
- ADMIN_PASSWORD_HASH (optional) – bcrypt hash to require x-api-pass header
- PORT=80, CORS_ORIGIN=*, DEBUG=true

To generate a bcrypt hash:
```bash
node -e "console.log(require('bcryptjs').hashSync('your-password', 10))"
```

## Security Notes
- All secrets passed via `--env-file` are encrypted to the TEE by the Phala CLI
- Private keys never leave the enclave
- Use ADMIN_PASSWORD_HASH to restrict API access in production

## Files
- docker-compose.yml – Phala-ready compose (80→80, env mapping)
- .env.example – quick bootstrap

## License
Apache-2.0

