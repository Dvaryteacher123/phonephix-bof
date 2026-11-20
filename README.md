
<div align="center">

<img src="https://i.ibb.co/N26rv2qt/27bc5646a677.jpg" alt="Phonephix Bot" width="420" />

# 👑 Phonephix Bot

**Secure · Fast · Powerful · Premium**

Developed by **Dvary** — Connect · Chat · Enjoy

[Join the Phonephix Pro channel](https://whatsapp.com/channel/0029VbCRC9b5fM5cruU8PF2M)

### 🚀 Get the bot in one click

<a href="https://github.com/Dvaryteacher123/phonephix-bof/fork"><img src="https://img.shields.io/badge/🍴_Fork_this_repo-24292f?style=for-the-badge&logo=github&logoColor=white" alt="Fork" height="42"></a>
<a href="https://github.com/Dvaryteacher123/phonephix-bof/archive/refs/heads/main.zip"><img src="https://img.shields.io/badge/⬇️_Download_ZIP-2ea44f?style=for-the-badge&logo=github&logoColor=white" alt="Download ZIP" height="42"></a>

<a href="https://render.com/deploy?repo=https://github.com/Dvaryteacher123/phonephix-bof"><img src="https://render.com/images/deploy-to-render-button.svg" alt="Deploy to Render" height="42"></a>
<a href="https://railway.com/new"><img src="https://railway.com/button.svg" alt="Deploy on Railway" height="42"></a>
<a href="#-vps--panel"><img src="https://img.shields.io/badge/🖥️_Deploy_on_VPS-0b5fff?style=for-the-badge&logo=linux&logoColor=white" alt="Deploy on VPS" height="42"></a>

</div>

> **Quick steps:** ① Fork or Download ZIP → ② Deploy → ③ Configure Environment Variables → ④ Open Logs → ⑤ Copy your Pair Code and link WhatsApp.

---

## ✨ How it works

One bot = one WhatsApp number.

1. Deploy the bot.
2. Set `WHATSAPP_NUMBER` with your country code.
3. Open Logs.
4. Copy the 8-character Pair Code.
5. On WhatsApp, go to Settings → Linked Devices → Link a Device → Link with phone number instead.
6. Enter your Pair Code.

---

## 🚀 Where to deploy

### Render

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/Dvaryteacher123/phonephix-bof)

1. Fork this repository.
2. Connect your fork to Render.
3. Create a Web Service or Background Worker.
4. Set Build Command:

```bash
npm install
```

5. Set Start Command:

```bash
npm start
```

6. Open Environment.
7. Add the variables listed below.
8. Save Changes and deploy.
9. Open Logs and get your Pair Code.

### ⚙️ Important Render Environment Variables

Add these variables in Render → Environment → Add Environment Variable.

| NAME | VALUE |
|---|---|
| `WHATSAPP_NUMBER` | `255712345678` |
| `YOUTUBE_DL_SKIP_PYTHON_CHECK` | `1` |
| `DATA_DIR` | `/data` |

**Python configuration**

The variable `YOUTUBE_DL_SKIP_PYTHON_CHECK=1` skips the Python version check used by youtube-dl-exec.

It does NOT install Python.

Python 3.11 or newer is still required for YouTube downloading functionality.

If YouTube downloading fails, make sure Python 3.11+ is installed in your deployment environment.

**Persistent Storage**

For session persistence:

1. Add a Persistent Disk.
2. Set mount path to `/data`.
3. Set `DATA_DIR=/data`.

Without persistent storage, WhatsApp sessions may be lost after restarts or redeployments.

---

### Railway

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/new)

1. Fork the repository.
2. Select Deploy from GitHub Repo.
3. Choose your fork.
4. Open Variables.
5. Add:

```env
WHATSAPP_NUMBER=255712345678
YOUTUBE_DL_SKIP_PYTHON_CHECK=1
DATA_DIR=/data
```

6. Add a Volume mounted at `/data`.
7. Open Deployments → Logs.
8. Copy your Pair Code.

Ensure Python 3.11+ is installed if using YouTube downloading.

---

### Heroku

1. Create a Heroku application.
2. Connect your GitHub repository.
3. Open Settings → Config Vars.
4. Add your environment variables.
5. Ensure the worker process is configured.
6. Open logs to get your Pair Code.

A persistent session requires suitable persistent storage. Do not assume local files survive dyno restarts.

---

## 🖥️ VPS / Panel

Works on Ubuntu / Debian with Node.js 20 or newer.

### 1. Install dependencies

```bash
sudo apt update
sudo apt install -y git curl python3 python3-pip
```

Install Node.js 20:

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm install -g pm2
```

Check versions:

```bash
node -v
python3 --version
```

Python 3.11+ is required for YouTube downloading.

### 2. Clone repository

```bash
git clone https://github.com/Dvaryteacher123/phonephix-bof.git
cd phonephix-bof
npm install
```

### 3. Configure Environment

```bash
cp .env.example .env
nano .env
```

Example:

```env
WHATSAPP_NUMBER=255712345678
YOUTUBE_DL_SKIP_PYTHON_CHECK=1
DATA_DIR=./session
BOT_NAME=Phonephix Bot
DEFAULT_PREFIX=.
BOT_MODE=public
BOT_TIMEZONE=Africa/Dar_es_Salaam
BOT_FOOTER=Powered by Phonephix
INTEGRITY_DEBUG=false
```

### 4. Start bot

```bash
pm2 start ecosystem.config.js
pm2 logs
```

Get your Pair Code from logs.

### 5. Keep bot online

```bash
pm2 save
pm2 startup
```

### Pterodactyl Panel

1. Upload your bot files.
2. Install dependencies using `npm install`.
3. Set Startup Command to `npm start`.
4. Open Environment Variables.
5. Add `WHATSAPP_NUMBER`.
6. Add `YOUTUBE_DL_SKIP_PYTHON_CHECK=1`.
7. Ensure Python 3.11+ is installed if YouTube downloading is needed.
8. Start the server.
9. Open Console and get your Pair Code.

---

## 🔑 Environment Variables

### Required

| Variable | Description |
|---|---|
| `WHATSAPP_NUMBER` | WhatsApp number with country code, without + or spaces |

### Storage

| Variable | Description |
|---|---|
| `DATA_DIR` | Session storage directory |

### Bot Configuration

| Variable | Description |
|---|---|
| `BOT_NAME` | Bot display name |
| `DEFAULT_PREFIX` | Command prefix |
| `BOT_MODE` | public or private |
| `BOT_TIMEZONE` | Bot timezone |
| `BOT_FOOTER` | Message footer |

### YouTube / Music

| Variable | Description |
|---|---|
| `YOUTUBE_DL_SKIP_PYTHON_CHECK` | Set to 1 to skip Python version check |
| `YT_PROXY` | Optional YouTube proxy |
| `MUSIC_PROVIDERS` | Music provider order |
| `SAAVN_API_URLS` | JioSaavn API addresses |
| `PIPED_INSTANCES` | Piped instances |
| `MUSIC_API_BASES` | Extra music API addresses |

### AI Configuration

| Variable | Description |
|---|---|
| `AI_API_KEY` | AI provider API key |
| `AI_API_URL` | AI API endpoint |
| `AI_MODEL` | AI model name |

Example:

```env
AI_API_URL=https://api.groq.com/openai/v1
AI_MODEL=llama-3.1-8b-instant
```

### Weather

| Variable | Description |
|---|---|
| `WEATHER_API_KEY` | OpenWeather API key |

### Security

| Variable | Description |
|---|---|
| `INTEGRITY_DEBUG` | Enable integrity debugging |

---

## 🌷 Menu

`.menu` displays available commands.

`.menu <category>` displays commands in a specific category.

---

## 🔒 Protection

- Only one session can run at a time.
- The bot is locked to the first linked number.
- Pair-code requests are limited.
- Shipped JavaScript files are protected by the project's integrity mechanism.
- Custom commands belong in `phonephix/custom/`.

Do not edit protected files unless you understand the integrity system.

---

## 🍴 Fork & Download

| Option | Link |
|---|---|
| Fork repository | https://github.com/Dvaryteacher123/phonephix-bof/fork |
| Download ZIP | https://github.com/Dvaryteacher123/phonephix-bof/archive/refs/heads/main.zip |

After forking:

1. Deploy your own repository.
2. Configure your own WhatsApp number.
3. Add your own API keys.
4. Keep your session files private.
5. Never upload `.env` to GitHub.

---

<div align="center">

# POWERED BY DVARY

**Phonephix Bot**

Connect · Chat · Enjoy

</div>
