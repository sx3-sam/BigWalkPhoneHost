# Big Walk Phone Host

Host a **Big Walk** multiplayer world straight from an Android phone. Your friends join
with a **6-letter code** from PC or console — **they install nothing**. No PC left running,
no server to rent.

Under the hood it's a fork of **Winlator** (Wine + Box64) plus a **BepInEx** plugin that runs
Big Walk headless as a dedicated server on the phone.

> ⚠️ **You bring your own copy of Big Walk** (from Steam). This app does **not** contain the game —
> it only sets up the hosting around a copy you already own. Everyone who hosts or joins already owns the game.

---

## ✨ Features
- **One-tap setup** — copy your plain Steam game folder onto the phone and tap *Set up the game mod*; the app installs BepInEx + the Direct Host plugin for you. No PC modding.
- **Join by 6-letter code** (Epic lobby) — friends on PC or console type it in Big Walk's Join menu, nothing extra to install.
- **Same Wi-Fi or over the internet** (via Tailscale).
- **Live dashboard** — CPU %, temperature, FPS and player count while you host.
- **Runs in the background** — the server keeps going when you leave the app; saves are copied back automatically every minute and on stop.
- **Voice-decode optimisation** (optional) — saves phone CPU in a full lobby; players still hear each other.

---

## 📋 Requirements
- An Android phone (Snapdragon-class; tested on a Snapdragon 680), kept **plugged in** while hosting.
- **Your own copy of Big Walk** (Steam), copied onto the phone.
- About **2 GB** of free storage.

---

## ⬇️ Install
1. Download the latest APK from the [**Releases**](../../releases) page.
2. Install it (allow *install from unknown sources* if Android asks).

---

## 🛠️ Setup (once — about 5 minutes)
1. **Copy your game onto the phone.** On your PC the game folder is usually:
   ```
   ...\Steam\steamapps\common\Big Walk
   ```
   Copy that **whole folder** to the phone at `Internal storage / Download / BigWalk`.
   It's a plain Steam copy — **no modding needed, the app does it.**
   *(Optional: put any `.sav` files in `Download/BigWalkSaves`.)*
2. **Install the app** (see above).
3. **Open the app → Setup tab.** You'll see three cards — Your phone, Your game, Network:
   - Tap **Allow storage access**
   - Tap **Install Wine + Box64** (~1–2 min)
   - Tap **Set up the game mod** (installs BepInEx + the Direct Host plugin)
   - Tap **Turn off battery optimisation**
   - When all three cards show a green ✓ it reads *"Everything's ready to host"*.

---

## 🎮 Host a game
1. **World tab** — pick a saved world or make a new one, set how many players, and choose who can join (Same Wi-Fi or Internet).
2. **Server tab → Start server.** About two minutes later a **6-letter code** appears, with live CPU / Temp / FPS / Players stats.

## 🤝 For your friends (joining)
- They need their **own copy of Big Walk** (any plain copy — nothing to install).
- In Big Walk: **Join → type the 6-letter code → password** (if one was set). Done.

---

## 🌐 Internet play
Same Wi-Fi works out of the box. For friends elsewhere, install **Tailscale** (free) on the phone
and on their PC, both signed into the same Tailscale account, then pick *Internet* when hosting.

## 🧰 Troubleshooting
- **Lag with a full lobby** → World tab → turn on *Stop server voice decoding*.
- **Logs & the join command** → Server tab → *Details*.
- First handshake over Wi-Fi can take up to a minute.

---

## 💜 Help & support
- **Need help?** Contact **Sx3.tt** on Discord (also linked inside the app).
- **Support the project:** [ko-fi.com/soulmods](https://ko-fi.com/soulmods) ☕

## 📄 Credits & legal
- Built on [Winlator](https://github.com/brunodev85/winlator) (Wine, Box64) and [BepInEx](https://github.com/BepInEx/BepInEx).
- **Big Walk** is © House House. It is **not** included in this project — bring your own legally-owned copy.
- This is a community tool for hosting your own game; it is not affiliated with or endorsed by House House.
