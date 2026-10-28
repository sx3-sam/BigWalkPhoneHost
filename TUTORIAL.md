# Big Walk Phone Host — Full Tutorial

A step-by-step guide to hosting a **Big Walk** world from your Android phone, from zero to
"my friends are in my world." If you just want the short version, see the [README](README.md).

> **The golden rule:** everyone who plays owns Big Walk on Steam. This app does **not** give
> anyone the game — it just turns a copy you already own into a server your phone runs. You need
> your own copy on the phone to host; your friends need their own copy to join.

---

## Table of contents
1. [What you need](#1-what-you-need)
2. [Get the game onto your phone](#2-get-the-game-onto-your-phone)
3. [Install the app](#3-install-the-app)
4. [Setup tab — get everything ready](#4-setup-tab--get-everything-ready)
5. [World tab — choose what to host](#5-world-tab--choose-what-to-host)
6. [Server tab — go live](#6-server-tab--go-live)
7. [How your friends join](#7-how-your-friends-join)
8. [Playing over the internet (Tailscale)](#8-playing-over-the-internet-tailscale)
9. [Troubleshooting](#9-troubleshooting)
10. [FAQ](#10-faq)
11. [Help & support](#11-help--support)

---

## 1. What you need
- **An Android phone.** A Snapdragon-class chip is recommended (developed and tested on a
  Snapdragon 680). Keep it **plugged in** while hosting — the server uses the CPU continuously.
- **Your own copy of Big Walk** from Steam, on your PC.
- **~2 GB free storage** on the phone (game + the app's Wine/Box64 layer).
- *(Optional)* **Tailscale** if you want friends outside your home Wi-Fi to join.

---

## 2. Get the game onto your phone
This is the one manual step, and it only happens once.

1. On your PC, open your Big Walk install folder. It's usually here:
   ```
   C:\Program Files (x86)\Steam\steamapps\common\Big Walk
   ```
   *(In Steam: right-click Big Walk → Manage → Browse local files.)*
2. Copy that **entire folder** to your phone at:
   ```
   Internal storage / Download / BigWalk
   ```
   - **USB cable:** plug the phone into the PC, allow file transfer, and drag the folder into `Download`, renaming it `BigWalk`.
   - **No cable?** Zip the folder, upload to Google Drive, download on the phone, and unzip into `Download/BigWalk`.
3. **Do not mod it.** Copy the plain Steam files — the app installs the mod for you in step 4.
4. *(Optional)* If you have existing save files (`.sav`), put them in `Download/BigWalkSaves`.

> ✅ When done, the phone should have `Download/BigWalk/Big Walk.exe` and
> `Download/BigWalk/GameAssembly.dll`.

---

## 3. Install the app
1. Download **`BigWalkPhoneHost-v0.2.apk`** from the [Releases page](../../releases).
2. Open it on the phone. Android will ask to **allow installing from unknown sources** —
   turn it on for your browser/files app, then tap **Install**.
3. Open **Big Walk Phone Host**.

---

## 4. Setup tab — get everything ready
![Setup tab](setup.png?v=2)

The Setup tab shows three cards. Work top to bottom; each turns green ✓ when it's done.

- **Your phone** — tap **Allow storage access**, then **Install Wine + Box64**. This unpacks the
  app's own Windows layer and creates the server container (takes 1–2 minutes). Then tap
  **Turn off battery optimisation** so Android doesn't pause your server.
- **Your game** — tap **Set up the game mod**. The app installs BepInEx and the Direct Host plugin
  onto your copy (about 10 seconds). No PC modding needed.
- **Network** — shows your Wi-Fi address. Tailscale is optional (only for internet play).

When the banner reads **"Everything's ready to host"**, tap **Pick a world**.

> 💜 The Setup tab also has **"Support soulmods on Ko-fi"** and **"Need help? Contact Sx3.tt on
> Discord"** at the bottom.

---

## 5. World tab — choose what to host
![World tab](world.png?v=2)

- **Your worlds** — pick a saved world from `Download/BigWalkSaves`, or choose **Fresh world**
  (plays but keeps nothing). Use **Import** to add a `.sav`, **Share** to export one.
- **New world** — type a name and tap **Use this new world**; the server creates it on first start.
- **How many friends** — 2, 3 or 4, the same world-size choice as the game. (The server still
  lets up to 11 players connect whichever you pick.)
- **Who can join:**
  - **Join code** — a 6-letter code; pick **Same Wi-Fi** or **Tailscale** for how friends reach you.
  - **Password** — classic IP + port + password (friends launch with `-join`).
  - **Epic** — the phone opens the game's own Epic lobby; friends type the code in Join, nothing to install. *(Recommended — works on PC and console.)*
- **Stop server voice decoding** *(experimental)* — turn on to save CPU in a full lobby; players
  still hear each other.

Tap **Save**, or **Save and start** to jump straight to hosting.

---

## 6. Server tab — go live
![Server tab](server.png?v=2)

1. Tap **Start server**. The first start takes about **two minutes** (Wine boots, the game loads,
   the plugin opens the lobby).
2. When the dot turns green and it says **Live**, your **6-letter code** appears.
3. The tiles show the live **CPU**, **temperature**, **FPS**, and **players** — green is healthy,
   amber is warm, red means the phone is struggling (lower players or turn on voice optimisation).
4. **Copy** or **Share** the code to send it to friends.
5. **Details** shows the exact join command, addresses, and the server log.

The server keeps running when you leave the app (a notification shows while it does). Tap **Stop**
to shut it down — your save is copied back to `Download/BigWalkSaves` automatically.

---

## 7. How your friends join
Your friends need **their own copy of Big Walk** (plain — nothing extra to install).

- **Epic / Join code:** in Big Walk, open **Join**, type the **6-letter code**, then the password
  if you set one. Works on PC and console.
- **Password mode:** they launch the game with the command shown under **Server → Details**, e.g.
  `-join <your-ip> -port <port> -password <password>`.

---

## 8. Playing over the internet (Tailscale)
Same Wi-Fi needs nothing extra. For friends elsewhere:

1. Install **Tailscale** (free) on the **phone** and on each friend's **PC**.
2. Sign everyone into the **same Tailscale account** (or share the network).
3. On the phone, open Tailscale once so it connects.
4. In the app's **World tab**, choose **Join code → Tailscale** (or Epic, which routes over the
   internet on its own).
5. Start the server and share the code.

---

## 9. Troubleshooting
- **"Copy your Big Walk folder…" won't go away** — check the files are at exactly
  `Download/BigWalk` (not `Download/BigWalk/BigWalk`). The app looks for `Big Walk.exe` there.
- **Server never reaches "Live"** — give it the full ~2 minutes on first start. Keep the phone
  plugged in and unlocked for the first boot. Check **Details → log** for errors.
- **Friends can't connect on Wi-Fi** — make sure everyone is on the same network; the first
  handshake can take up to a minute. For internet, use Tailscale or Epic.
- **Lag / stutter with several players** — turn on **Stop server voice decoding** (World tab) and
  restart; lower the player count; keep the phone cool and charging.
- **The phone gets hot** — normal under load; keep it charging and in a cool spot. Watch the Temp tile.

---

## 10. FAQ
- **Do my friends need this app?** No — only the host does. Friends use their normal game.
- **Do my friends need to mod their game?** No. A plain Steam copy joins fine.
- **Is the game included in the APK?** No. You bring your own copy; the APK is ~200 MB of Wine +
  Box64 + the mod, not the game.
- **Can I host without owning Big Walk?** No — you need the game files to run the server.
- **Does it keep running in the background?** Yes, with a notification. Keep it charging.
- **Where are my saves?** `Download/BigWalkSaves`, updated every minute and when you stop.

---

## 11. Help & support
- **Need help?** Contact **Sx3.tt** on Discord (also linked in the app's Setup tab).
- **Enjoying it?** Support the project on Ko-fi: **https://ko-fi.com/soulmods** ☕

---
*Big Walk Phone Host v0.2. Built on Winlator (Wine + Box64) and BepInEx. Big Walk © House House —
not affiliated or endorsed.*
