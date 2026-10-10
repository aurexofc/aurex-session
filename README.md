# 👑 AUREX Session Server

Pair a WhatsApp number via pairing code, get a `SESSION_ID` for the AUREX bot.
**One-shot:** pairing code → pair in WhatsApp → SESSION_ID → done. No 24/7 server needed.

## Deploy on Vercel

1. Import this repo in [Vercel](https://vercel.com)
2. Deploy — no build settings needed
3. Open the site → enter number → **quickly** enter the pairing code in
   WhatsApp (Linked Devices → Link with phone number) → copy SESSION_ID

> ⚠️ Vercel caps a request at ~60 seconds — enter the pairing code
> **within a minute**. If it times out, just try again.

## Local / VPS (no time limit)

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
