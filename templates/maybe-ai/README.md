# Maybe Finance on Phala Cloud

Deploy [Maybe Finance](https://github.com/maybe-finance/maybe), an open-source personal finance management app, on Phala Cloud's TEE infrastructure.

## Features

- 💰 **Complete Financial Management**: Track expenses, budgets, investments, and net worth
- 🏦 **Bank Syncing**: Connect bank accounts via Plaid (requires API key)
- 📊 **Beautiful Analytics**: Visualize spending patterns and financial trends
- 🤖 **AI Assistant**: Smart financial insights and rule suggestions (requires OpenAI key)
- 🔒 **Privacy-First**: Self-hosted in TEE for maximum security
- 📱 **Modern UI**: Clean, responsive interface built with Rails & Hotwire

## Quick Start

### 1. Set Up Environment

Create a `.env` file with required configuration:

```bash
# Generate a secret key
openssl rand -hex 64

# Add to .env file:
SECRET_KEY_BASE=<your-generated-key>
POSTGRES_PASSWORD=<choose-a-strong-password>

# Optional: Add OpenAI key for AI features
# OPENAI_ACCESS_TOKEN=sk-your-openai-api-key
```

### 2. Deploy to Phala Cloud

```bash
# Deploy the application
phala cvms create -c docker-compose.yml -e .env --name maybe-finance

# Check deployment status
phala cvms list
```

### 3. Access Your App

After deployment completes:
1. Visit: `https://<your-app-id>-3000.teehouse.phatfn.xyz`
2. Create your account
3. Start managing your finances!

## Configuration

### Required Environment Variables

- `SECRET_KEY_BASE`: Rails session encryption key (generate with `openssl rand -hex 64`)
- `POSTGRES_PASSWORD`: Database password

### Optional Features

- **AI Assistant**: Set `OPENAI_ACCESS_TOKEN` to enable smart insights
- **Bank Connections**: Configure Plaid credentials (see Maybe docs)
- **Email Notifications**: Configure SMTP settings

## Deployment Journey & Solutions

### Challenge: Rails CSRF Protection in TEE

**Issue**: Users couldn't create accounts - got "The change you wanted was rejected" (422 error)

**Root Cause**: Rails was generating HTTP URLs while Phala Cloud serves over HTTPS, causing CSRF token validation failures

**Solution**: Configure Rails to understand it's behind an HTTPS proxy:
```yaml
RAILS_FORCE_SSL: "false"  # Don't enforce SSL (TEE handles it)
RAILS_ASSUME_SSL: "true"   # But assume we're on HTTPS
```

### Challenge: Host Authorization

**Issue**: Rails rejected requests from Phala Cloud domains

**Solution**: Clear host restrictions and use DSTACK variables:
```yaml
APP_DOMAIN: "${DSTACK_APP_ID}-3000.${DSTACK_GATEWAY_DOMAIN}"
# Plus: Rails.application.config.hosts.clear in entrypoint
```

### Challenge: Invite Code Requirement

**Issue**: Default self-hosted mode requires invite codes

**Solution**: Disable requirement on first run:
```bash
Setting.require_invite_for_signup = false
```

## Architecture

```
┌─────────────────────────────────────┐
│         Phala Cloud TEE             │
├─────────────────────────────────────┤
│  ┌─────────┐  ┌─────────┐          │
│  │  Rails  │  │ Sidekiq │          │
│  │  (3000) │  │ Worker  │          │
│  └────┬────┘  └────┬────┘          │
│       │            │                │
│  ┌────┴────────────┴────┐          │
│  │    PostgreSQL 16     │          │
│  └──────────────────────┘          │
│  ┌──────────────────────┐          │
│  │      Redis 7         │          │
│  └──────────────────────┘          │
└─────────────────────────────────────┘
```

## Advanced Configuration

### Enable AI Features

```bash
# Add to .env
OPENAI_ACCESS_TOKEN=sk-your-openai-api-key

# Upgrade deployment
phala cvms upgrade <app-id> -c docker-compose.yml -e .env
```

### Connect Bank Accounts

See [Maybe's Plaid documentation](https://github.com/maybe-finance/maybe/wiki) for bank syncing setup.

## Troubleshooting

### Registration Issues

If you see "The change you wanted was rejected":
1. Check deployment logs for errors
2. Ensure `RAILS_ASSUME_SSL: "true"` is set
3. Verify password meets requirements:
   - Minimum 8 characters
   - Upper and lowercase letters
   - At least one number
   - At least one special character

### Database Connection

If the app won't start:
1. Check if PostgreSQL is healthy: `phala cvms get <app-id>`
2. Ensure `POSTGRES_PASSWORD` matches in all services
3. Wait a few minutes for initial database setup

## Security Considerations

- All data is encrypted within the TEE
- Passwords are hashed using bcrypt
- Session cookies are encrypted with `SECRET_KEY_BASE`
- Bank credentials (if used) are stored encrypted
- No data leaves the TEE without your explicit action

## Resources

- [Maybe Finance GitHub](https://github.com/maybe-finance/maybe)
- [Maybe Documentation](https://github.com/maybe-finance/maybe/wiki)
- [Phala Cloud Dashboard](https://cloud.phala.network/dashboard/)

## License

Maybe Finance is open source under the AGPL-3.0 license. This template is provided as-is for deployment on Phala Cloud.