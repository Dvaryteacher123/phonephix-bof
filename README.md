<div align="center">

<img src="https://i.ibb.co/N26rv2qt/27bc5646a677.jpg" alt="Phonephix Bot" width="420" />

# 👑 Phonephix Bot

**Secure · Fast · Powerful · Premium**

Developer by **Dvary** — Connect · Chat · Enjoy

[Join the Phonephix Pro channel](https://whatsapp.com/channel/0029VbCRC9b5fM5cruU8PF2M)

</div>

---

## ✨ How it works

One bot = one WhatsApp number. No website, no Telegram.

1. **Deploy** the bot (Render, Railway, Heroku, VPS or a panel).
2. Set your number in **Environment Variables** (`WHATSAPP_NUMBER`), e.g. `255712345678`. No `+`, no spaces.
3. Open the **Logs**. The bot will show an **8-character PAIR CODE**.
4. On WhatsApp: **Settings → Linked Devices → Link a Device → Link with phone number instead**, then enter the code.
5. Once linked, your number automatically follows the Phonephix Pro channel.

---

## 🚀 Where to deploy

### Render
1. Create **New → Web Service** (or **Background Worker**) and connect your repo.
2. **Build Command:** `npm install`
3. **Start Command:** `npm start`
4. Open the **Environment** tab → **Add Environment Variable** → set `WHATSAPP_NUMBER`.
5. Add a **Persistent Disk**, e.g. mount path `/data`, then set `DATA_DIR=/data`.
6. Click **Deploy**, then open **Logs** to get your pair code.

### Railway
1. **New Project → Deploy from GitHub repo**.
2. Open the **Variables** tab → set `WHATSAPP_NUMBER`.
3. Add a **Volume**, e.g. mount path `/data`, then set `DATA_DIR=/data`.
4. Open **Deployments → Logs** to get your pair code.

### Heroku
1. Create a new app and connect your repo.
2. **Settings → Config Vars** → set `WHATSAPP_NUMBER`.
3. A `Procfile` is included (`worker: node server.js`). Turn on the **worker** dyno, not web.
4. Open **More → View logs** to get your pair code.
5. Heroku has no persistent disk, so you will have to pair again after every restart. For long-term use, choose Render, Railway or a VPS.

### VPS / Panel
```bash
npm install
npm start
```
The bot will ask for your number in the console. On a VPS you can also use PM2:
```bash
npm i -g pm2
pm2 start ecosystem.config.js
pm2 save && pm2 startup
```

---

## 🔑 Environment Variables (where to put them)

| Platform | Where to set them |
|---|---|
| Render | **Environment** tab |
| Railway | **Variables** tab |
| Heroku | **Settings → Config Vars** |
| VPS / Panel | A `.env` file (copy from `.env.example`) or the panel's Environment section |

> ⚠️ Never commit your `.env` file to GitHub. Keep every secret (keys, numbers) in Environment Variables only.

### Required

| Variable | Description |
|---|---|
| `WHATSAPP_NUMBER` | Your number with country code, e.g. `255712345678`. Needed on Render, Railway and Heroku |
| `DATA_DIR` | Folder on a persistent disk (e.g. `/data`). Without it you must pair again after every redeploy |

### Optional

| Variable | Description |
|---|---|
| `BOT_NAME` | Bot name |
| `DEFAULT_PREFIX` | Command prefix, e.g. `.` |
| `BOT_MODE` | `public` or `private` |
| `BOT_TIMEZONE` | e.g. `Africa/Dar_es_Salaam` |
| `BOT_FOOTER` | Footer text shown on messages |
| `AI_API_KEY` | AI key (Groq, OpenAI, OpenRouter) for the `.ai` commands |
| `AI_API_URL` | e.g. `https://api.groq.com/openai/v1` |
| `AI_MODEL` | e.g. `llama-3.1-8b-instant` |
| `WEATHER_API_KEY` | OpenWeather key for `.weather` |
| `MUSIC_PROVIDERS` | Order of music sources |
| `SAAVN_API_URLS` | JioSaavn API addresses, comma separated |
| `PIPED_INSTANCES` | Piped instances, comma separated |
| `MUSIC_API_BASES` | Extra YouTube-download API addresses |
| `YT_PROXY` | Optional proxy for YouTube |

The full list is in `.env.example`. After changing any variable, **restart** the bot.

---

## 🌷 Menu

`.menu` shows every command in categories. `.menu <category>` shows a single category.

---

## 🔒 Protection

- Only one session can run at a time.
- The bot is locked to the first number that linked. If a different number logs in, the session is deleted.
- Every shipped `.js` file is fingerprinted in a signed manifest. If any of them is **edited or deleted**, the bot shuts down.
- Adding new files (your own commands, docs) is fine. Put your own commands in `phonephix/custom/`.
- Pair-code requests are limited (4 per hour, 45 seconds apart).

> To see which file triggered a shutdown, set `INTEGRITY_DEBUG=true` and start the bot once.

---

## 🍴 Forking on GitHub

1. Click **Fork**.
2. Deploy your fork using any option above.
3. Put **your own** keys in Environment Variables.
4. Do not edit the shipped `.js` files.

<div align="center">

**POWERED BY DVARY**

Connect · Chat · Enjoy

</div>
