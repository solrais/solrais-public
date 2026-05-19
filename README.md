# 🤤 Solrais — Macro Tracker & AI Assistant

> Solrais is currently on **version v1.4.3** — a *PRIVATE* Discord bot for **macro session tracking**, **AI-powered chat**, **biome relay systems**, and more ig

![Version](https://img.shields.io/badge/version-v1.4.3-blue?style=flat-square)
![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/license-Private-red?style=flat-square)

---

## ⚠️ NOTICE

> [!IMPORTANT]
> The repository containing the actual code is **PRIVATE**. It is not available for public download or distribution. Solrais runs exclusively on our servers. Do not share, distribute, or publish any part of this code without explicit permission.
-# well u cant anyway the code is private lol

> [!CAUTION]
> **This is not a self-hosted bot.** Solrais is operated on private servers and accessed through Discord. No download or self-hosting option is available.
-# yoo staff pls dont leak the dashboard link its not protected ok thanks :D

---

## 💅 AI Chat System

Solrais features a **full AI chat system** powered by Groq API with access to real-time server data. Unlike basic chatbots, Solrais can actually **look up information** and **perform actions** using callable tools. Solrais is currently mainly powered by gpt-oss-120b (high), I must also warn users that AI can make mistakes and this one is NOTERIOUS for making mistakes constantly, please be careful on the info given by the AI and always double-check

### How It Works

Mention Solrais or use the `s.` prefix to start chatting. The AI has:

- **🧠 Memory & Profile Learning** — Solrais remembers how you talk, your personality traits, interests, and writing style. The more you chat, the more personalized responses become. (CAN be disabled with a command)
- **🔧 20+ Callable Tools** — Instead of guessing, Solrais runs actual tools to fetch data:
  - Query user stats, sessions, and leaderboard positions
  - Search the knowledge base for Sol's RNG mechanics, auras, potions, and biomes
  - Look up server members and their macro activity
  - Find users by username with fuzzy/typo-tolerant matching
  - Generate images using the Magnific API
  - Analyze images sent in chat
  - Look up answers on the internet
- **🎯 Smart Context** — Understands follow-up questions, comparisons ("who has more hours, X or Y?"), and multi-turn conversations.
- **📸 Vision Support** — Send Solrais an image and it can analyze what's in it.
- **🛡️ Content Filtering** — Built-in safeguard pipeline checks responses for consistency and safety before posting.

### Example Things You Can Ask

> *"How many total hours does dxrkfire have?"*
> *"Compare my stats with n3ru's"*
> *"What's the rarest aura in Sol's RNG?"*
> *"Show me the leaderboard for this week"*
> *"Generate an image of a glitch biome"*
> *"What does this screenshot show?"*

### Solrais is powered by multiple AIs, such as:
- gpt-oss-120b (high) for talking and tool calling
- qwen3-32b for tool calling
- llama-4-scout-17b-16e-instruct for vision
- orpheus-v1-english (might be deprecated soon) for TTS
- whisper-3 for STT
---

## 🌟 Features

### 📊 Macro Session Tracking
- **Auto-detection** of macro start/stop events from webhooks
- **Live session stats** — duration, biome count, streak tracking
- **Per-user history** surviving restarts and reboots
- **Multi-software support** — MultiScope, Coteab Macro, SolsScope, Maxstellar's Biome Macro, J.Jram, fishSol, EggSol, and auto compatibility (temporary) with other un-registered macros (like DroidScope i forogr to register it)
- **Macro version detection** and optional blacklisting

### 🌐 Biome Relay System
- **Rare biome alerts** — Glitch, Dreamspace, Cyberspace relayed with @everyone pings
- **Delay-based relays** — Hell, Heaven, Starfall, Corruption, Null, Sandstorm with configurable delays per role
- **Weather system** — Windy, Rainy, Snowy forwarded automatically
- **Free biome webhooks** — all free biomes routed through dedicated channels
- **Merchant alerts** — Mari, Jester, Rin detected and relayed to designated channels

### 👥 User & Rank Management
- **AFK system** — `/afk` removes macroer roles, `/unafk` restores them with channel cleanup
- **Dormant system** — `/dormant` archives inactive users, `/undormant` reinstates roles and channels
- **Roblox verification** — `/link_roblox` checks RoVer registry or does manual code-based verification
- **Auto-role assignment** — verified/unverified roles, macroer rank, and dormant roles managed automatically
- **Inactivity warnings** — automatic pings after 3+ days of no macro activity
- **Auto-cleanup** — user data cleaned 48 hours after leaving the server

### 🏆 Leaderboards & Stats
- **Live leaderboards** — total hours, current sessions, weekly rankings
- **Achievement system** — unlockable achievements with daily quests
- **Activity breakdown** — per-category and per-user macro activity over configurable time windows
- **Session history** — detailed logs of every macro session with biome stats

### 🛠️ Staff Tools
- **`/fix_missing_rank`** — restore macroer rank to users who lost it due to bugs
- **`/force_roblox_link`** — manually link a Discord user to a Roblox account
- **`/force_assign` / `/force_unassign`** — manage channel assignments
- **`/macro_block`** — block specific macro versions server-wide
- **`/category`** — manage tracked Discord categories
- **`/create_webhook`** — generate webhook URLs for macro channels
- **`/node_restart`** — restart relay nodes remotely
- **`/check_webhooks`** — scan and validate webhook configurations
- **`/check_activity`** — deep-dive activity audit per category
- **`/maintenance`** — toggle maintenance mode to block all user commands

### 🖥️ Web Dashboard
- Real-time overview: active macroers, session count, total hours, biomes detected
- Relay node status with online/offline indicators
- One-click relay node restart from browser
- Top 25 leaderboard view
- Maintenance mode toggle
- Discord OAuth2 authentication for secure access

### 🐕 Watchdog System
- **Dedicated handler** monitors the main bot and all relay nodes 24/7
- Automatic alerts when any node goes offline
- Auto-clearing alerts when the node recovers
- Configurable ping role for watchdog notifications

---

## 🔧 Architecture

Solrais runs as a **distributed multi-node system**:

```
Discord ──► Relay Bot 1 ──► Main Bot ──► Dashboard
          ──► Relay Bot 2 ──► Main Bot ──► AI (Groq API)
          ──► Relay Bot 3 ──► Main Bot ──► Webhooks
          ──► Watchdog Handler (monitors everything)
```

- **Relay bots** (3 nodes) receive webhooks from macro clients and forward them
- **Main bot** processes sessions, relays, commands, and AI
- **Watchdog handler** keeps everything alive and alerts staff on failure
- **Web dashboard** provides live status and remote control

---

## 🎮 Commands Overview

### User Commands
| Command | Description |
|---------|-------------|
| `/stats` | View your macro statistics and data path |
| `/myprogress` | 7-day activity graph |
| `/leaderboards` | View macro leaderboard |
| `/daily` | Daily quest status |
| `/achievements` | View your unlocked achievements |
| `/link_roblox` | Link your Roblox account for verification |
| `/bugfix` | Report a bug |
| `/suggestion` | Submit a suggestion |

### AI Chat
| Trigger | Behaviour |
|---------|-----------|
| `@Solrais` | Ping the bot to start an AI conversation |
| `s.<message>` | Prefix any message with `s.` to chat |
| Image in chat | Solrais can analyze images you send |

### Staff Commands
| Command | Description |
|---------|-------------|
| `/fix_missing_rank` | Restore macroer rank to affected users |
| `/force_roblox_link` | Force-link a Discord user to a Roblox account |
| `/category` | Manage tracked categories |
| `/solraisconfig` | Configure delays, weather, and webhooks |
| `/macro_block` | Block macro versions |
| `/node_restart` | Restart relay nodes |
| `/maintenance` | Toggle maintenance mode |
| `/check_activity` | Activity audit |

---

## 🏗️ Project Structure

```
src/
├── bot/server/          — Slash commands, config UI, interactions
├── services/server/     — Core logic: AI, macros, relays, webhooks
└── utils/server/        — Data layer, constants, config handler
relay-bot-{1..3}/        — Relay nodes for webhook processing
handler/                 — Watchdog system
server.js                — Express web dashboard
data/                    — Runtime data (users, config, sessions)
```

---

## 📜 License

**PRIVATE** — All rights reserved. This code is the exclusive property of its owner.

> [!CAUTION]
> **Do not share, redistribute, or use this code without permission.**
> Solrais is a private service — no public downloads, self-hosting, or distribution.

---

*Built and maintained by **dxrkfire** & **n3ru__** for the Solrais community.*
