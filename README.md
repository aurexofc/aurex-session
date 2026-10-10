# 👑 AUREX Session Server

Pair a WhatsApp number via pairing code, get a `SESSION_ID` for the AUREX bot.

## Deploy on Vercel

1. Import this repo in [Vercel](https://vercel.com)
2. Deploy (no build settings needed)
3. Open the site → enter number → get pairing code → link in WhatsApp → copy SESSION_ID

> ⚠️ **Note:** Vercel serverless functions are short-lived. The pairing socket
> must stay alive while you enter the code in WhatsApp — keep the page open
> and complete pairing quickly. For 24/7 reliability, run `node server.js`
> on a VPS instead (`npm install && node server.js`).

## Local / VPS

```bash
npm install
node server.js
# → http://localhost:3001
```

## Env

| Var | Required | Purpose |
|-----|----------|---------|
| `PORT` | no | default 3001 |
| `ACCESS_KEY` | no | password-gate the site |
