# Notes

## Worker Status: Disabled

The `moltbot-sandbox` worker has been disabled as of 2026-02-14. It will not respond to requests on its `workers.dev` subdomain. The cron trigger (`*/5 * * * *`) has also been removed.

### Re-enable via API

```bash
curl -s -X POST 'https://api.cloudflare.com/client/v4/accounts/21e83a659e53610d961cb88ce68efc61/workers/scripts/moltbot-sandbox/subdomain' \
  -H 'Authorization: Bearer <your-cloudflare-token>' \
  -H 'Content-Type: application/json' \
  -d '{"enabled":true}'
```

### Re-enable via deploy

```bash
npx wrangler deploy
```

This will redeploy and automatically re-enable the worker and restore the cron trigger.
