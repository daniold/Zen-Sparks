# 🎇 Zen Sparks — Idle Game

> A relaxing, visually satisfying HTML5 idle game where sparks orbit a glowing Heart Crystal, generating energy as you upgrade, ascend, and climb the global leaderboard.

---

## ✨ Features

### 🎮 Core Gameplay
- **Mesmerizing Canvas Graphics** — Smooth, particle-based animations rendered on an HTML5 Canvas
- **Idle & Offline Progress** — Keep earning energy even when the tab is closed; your sparks never sleep

### ⚡ Upgrades

| Upgrade | Effect |
|---|---|
| **Sparks** | More sparks = more hits = more energy |
| **Power** | Increases base energy earned per hit |
| **Speed** | Makes sparks fly faster for more hits/sec |
| **Crit %** | Chance to land a critical hit for **5× energy** |

### 🌌 Ascension (Prestige)
Reset your progress in exchange for **Ascension Points (AP)**, which grant a **permanent global multiplier** to all future energy gains. The further you go, the faster you grow.

### 🏆 Global Leaderboard
Real-time **Top 50 leaderboard** powered by Firebase Firestore — see your exact rank among all players worldwide.

### 🎁 Player Interaction
Gift energy to other players, anonymously if you choose.

### 🎨 Custom Themes
Switch between visual styles to match your mood:
- 🌌 **Default** — Deep space vibes
- 🎃 **Spooky Halloween** — Pumpkin crystal chaos
- ❄️ **Winter Holiday** — Frosty snowflake crystal

---

## 🎮 How to Play

1. **Watch it Grow** — Sparks automatically fly toward the Heart Crystal. Every hit generates Energy.
2. **Upgrade** — Spend Energy on more Sparks, faster Speed, higher Power, or better Crit chance.
3. **Set a Name** — Click **"Set Name"** to claim your spot on the live Leaderboard.
4. **Ascend** — Once you hit **1 Million Energy**, reset your run for Ascension Points and a permanent boost.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, Vanilla JavaScript (ES6 Modules) |
| Styling | Tailwind CSS (via CDN) |
| Backend / DB | Firebase (Anonymous Auth + Firestore) |
| Rendering | HTML5 `<canvas>` API |

---

## 🚀 Setup & Self-Hosting

Zen Sparks uses Firebase for its real-time leaderboard and multiplayer features. You'll need your own Firebase project to run it.

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/zen-sparks.git
```

### 2. Create a Firebase Project
1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Create a new project
3. Enable **Firestore Database** *(start in production mode)*
4. Enable **Authentication** → turn on **Anonymous** sign-in

### 3. Set Firestore Security Rules
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /players/{userId} {
      allow read: if true;
      allow write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

### 4. Configure the App
When you first load `index.html`, the game will prompt you to paste your **Firebase Configuration object**. You can find this in your Firebase Project Settings under **Web App**.

---

## 📄 License

This project is open source. Feel free to fork, remix, and build on it!
