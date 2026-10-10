# 👑 AUREX Session Server

Alag website — WhatsApp number link karo, **SESSION_ID** nikalo, bot ke `.env` mein paste karo. Dobara pairing ki zaroorat nahi.

## Flow

1. Website kholo → number likho (country code ke saath, masalan `923001234567`)
2. Pairing code milega → WhatsApp → **Linked devices → Link with phone number** → code dalo
3. Connect hote hi **SESSION_ID** screen pe aa jayegi → Copy
4. Bot ke `.env` mein add karo:
   ```
   SESSION_ID=<paste>
   ```
5. Bot restart — pairing code **dobara nahi aayega** ✅

## VPS Deploy (ek command)

```bash
cd ~ && rm -rf aurex-session-server && unzip -o aurex-session-server.zip -d aurex-session-server \
&& cd aurex-session-server && npm install --omit=dev \
&& (pm2 delete aurex-session 2>/dev/null; pm2 start server.js --name aurex-session) \
&& pm2 save && echo "✅ Chal raha hai — port 3001"
```

Phir kholo: `http://VPS-IP:3001`

> **Node 24+ zaroori hai** (built-in SQLite ke liye). Agar pm2 nahi hai: `npm i -g pm2`

## Optional: password lagao

`.env` banao:
```
PORT=3001
ACCESS_KEY=koi-mushkil-password
```
Phir restart: `pm2 restart aurex-session`

## Safety

- Session 10 minute mein auto-delete (use ho ya na ho)
- SESSION_ID milte hi server se delete
- Ye tumhare WhatsApp login ki chaabi hai — **kisi ko mat dena**, website pe ACCESS_KEY lagao
