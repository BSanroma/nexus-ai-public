<div align="center">

![Nexus AI Banner](https://remote-nexus.dev/assets/banner-social.jpg)

# 🤖 Nexus AI — Pocket DevOps
### Leave the laptop at home. Manage your local projects via Telegram.

[![Status](https://img.shields.io/badge/Status-Live-success?style=for-the-badge&color=00d2ff)](https://remote-nexus.dev)
[![Platform](https://img.shields.io/badge/Platform-macOS%20%7C%20Windows%20%7C%20Linux-blue?style=for-the-badge&color=6e72fc)](https://remote-nexus.dev)
[![Security](https://img.shields.io/badge/Security-Sandbox%20%2B%20Rate%20Limiting-green?style=for-the-badge&color=2ecc71)](https://remote-nexus.dev)
[![License](https://img.shields.io/badge/License-Commercial-orange?style=for-the-badge&color=f1c40f)](https://remote-nexus.dev)

[**🌐 OFFICIAL WEBSITE**](https://remote-nexus.dev) · [**📦 GET NEXUS**](https://remote-nexus.dev) · [**📖 INSTALL GUIDE**](https://remote-nexus.dev)

</div>

---

## 🚀 The Vision

**Nexus AI** is a local-first AI daemon that bridges your machine and your pocket. Execute terminal commands, manage git repositories, and check logs securely from **Telegram** — without ever exposing your code to the cloud.

> *"Why be chained to your desk just to check a server log? Go outside. Nexus keeps you connected."*

## ✨ Key Features

| Feature | Description |
|---|---|
| **📱 Zero-Latency Control** | Run `npm test`, `docker ps`, or `git status` directly from Telegram chat. |
| **🔒 Local-First Security** | Your code **NEVER** leaves your machine. Nexus runs on localhost only. |
| **🗣️ Voice Commands** | Send a voice note: *"Check the API logs"* → Nexus executes and replies. |
| **🛡️ Owner-Only Access** | Strict `OWNER_ID` filter. The bot ignores every message except yours. |
| **⚡ AI-Powered Interpretation** | Powered by Google Gemini. Natural language → shell commands. |
| **🔑 BYOK (Bring Your Own Key)** | You use your own Gemini API key and Telegram bot. Zero cost for us, full control for you. |

## 🛡️ Security Architecture

Nexus takes security **very seriously**. Since it executes commands on your local machine, we've implemented multiple layers of protection:

### 🚫 Blocked Commands (Never Execute)
Commands that could destroy your system are **permanently blocked** and cannot be executed, even with confirmation:
```
rm -rf /    rm -rf /*    mkfs    dd if=    > /dev/    chmod 777 /    fork bombs
```

### ⚠️ Dangerous Command Detection (Dry-Run Mode)
Risky commands trigger a **confirmation prompt** with inline buttons before execution:
```
rm    sudo    chmod    chown    curl|sh    wget|sh    eval()
npm publish    git push --force    git reset --hard    DROP    DELETE FROM
shutdown    reboot    kill -9
```
When detected, Nexus shows:
```
⚠️ Dry-Run Mode: Potentially dangerous command detected:

`sudo systemctl restart nginx`

Confirm execution?
[✅ Execute]  [❌ Cancel]
```

### ⏳ Rate Limiting
- **Max 100 commands/hour** — Prevents accidental loops or abuse.
- **2-second cooldown** between commands — Protects against spam.
- **60-second auto-expire** on pending confirmations.

### 🔐 OWNER_ID Filtering
Every single message is checked against your unique Telegram `OWNER_ID`. No exceptions. If someone else finds your bot, they get:
```
⛔ Access denied. This is a private bot.
```

## 🔑 BYOK — Bring Your Own Key

Nexus AI uses a **BYOK model**. This means:

- **You create your own Telegram Bot** via [@BotFather](https://t.me/BotFather).
- **You provide your own [Google Gemini API Key](https://aistudio.google.com/apikey)**.
- **We store nothing.** All keys live in your local `.env` file on your machine.
- **Our operational cost per user is zero.** That's why a $3 lifetime license is sustainable.

## 📦 Installation

Nexus AI is distributed as a **standalone binary** for macOS, Windows, and Linux.

### 60-Second Setup:

**macOS / Linux:**
```bash
cd ~/Downloads
chmod +x nexus-bot-macos    # or nexus-bot-linux
./nexus-bot-macos
```
> ⚠️ macOS users: If Gatekeeper blocks it, go to **System Settings → Privacy & Security → "Open Anyway"**.

**Windows:**
```powershell
cd %USERPROFILE%\Downloads
nexus-bot-win.exe
```
> ⚠️ If Windows Defender blocks it: Click **"More info" → "Run anyway"**.

### Configuration:
On first run, Nexus will ask for:
1. Your **Telegram Bot Token** (from @BotFather)
2. Your **Gemini API Key** (from Google AI Studio)
3. Your **Telegram User ID** (your OWNER_ID)
4. Path to your **projects folder**

## 🏗️ Architecture

```
┌─────────────┐     ┌──────────────┐     ┌─────────────────┐
│  Telegram    │◄───►│  Nexus AI    │◄───►│  Your Local     │
│  (Phone)     │     │  Daemon      │     │  Projects       │
└─────────────┘     │              │     └─────────────────┘
                    │  🛡️ Security │
                    │  Module      │
                    │              │
                    │  🤖 Gemini   │
                    │  AI Engine   │
                    └──────────────┘
                    Runs on YOUR machine
                    Nothing leaves localhost
```

## ❓ FAQ

**Q: Who pays for the Gemini API?**
A: You do, with your own API key. Gemini 2.5 Flash costs ~$0.001 per command. A typical user spends ~$4/month.

**Q: Is my code uploaded anywhere?**
A: No. Nexus runs 100% on your machine. It's a bridge, not a vault.

**Q: Can someone else control my bot?**
A: No. OWNER_ID filtering is enforced on every message. Only your Telegram account can interact with the bot.

**Q: What if the AI hallucinates a dangerous command?**
A: The Security Module catches it. Dangerous commands require ✅/❌ confirmation. Destructive commands are permanently blocked.

**Q: $3 lifetime — is this sustainable?**
A: Yes. BYOK means we have zero ongoing costs per user. No servers, no API bills, no cloud infrastructure.

## 📥 Get Nexus AI

[**Get Nexus AI for $3 — Lifetime License (Early Access)**](https://remote-nexus.dev)

---

<div align="center">
Created with ❤️ by <b>Bernat Sanromà</b>
<br>
<a href="https://github.com/BSanroma">github.com/BSanroma</a>
<br><br>
<i>Defending critical thinking via advanced tech.</i>
</div>
