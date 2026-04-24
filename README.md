# 🎇 Zen Sparks — Idle Game
2
 
3
> A relaxing, visually satisfying HTML5 idle game where sparks orbit a glowing Heart Crystal, generating energy as you upgrade, ascend, and climb the global leaderboard.
4
 
5
---
6
 
7
## ✨ Features
8
 
9
### 🎮 Core Gameplay
10
- **Mesmerizing Canvas Graphics** — Smooth, particle-based animations rendered on an HTML5 Canvas
11
- **Idle & Offline Progress** — Keep earning energy even when the tab is closed; your sparks never sleep
12
13
### ⚡ Upgrades
14
| Upgrade | Effect |
15
|---|---|
16
| **Sparks** | More sparks = more hits = more energy |
17
| **Power** | Increases base energy earned per hit |
18
| **Speed** | Makes sparks fly faster for more hits/sec |
19
| **Crit %** | Chance to land a critical hit for **5× energy** |
20
 
21
### 🌌 Ascension (Prestige)
22
Reset your progress in exchange for **Ascension Points (AP)**, which grant a **permanent global multiplier** to all future energy gains. The further you go, the faster you grow.
23
 
24
### 🏆 Global Leaderboard
25
Real-time **Top 50 leaderboard** powered by Firebase Firestore — see your exact rank among all players worldwide.
26
 
27
### 🎁 Player Interaction
28
Gift energy to other players, anonymously if you choose.
29
 
30
### 🎨 Custom Themes
31
Switch between visual styles to match your mood:
32
- 🌌 **Default** — Deep space vibes
33
- 🎃 **Spooky Halloween** — Pumpkin crystal chaos
34
- ❄️ **Winter Holiday** — Frosty snowflake crystal
35
36
### 🛡️ Admin Dashboard
37
A built-in developer console for managing players, monitoring live stats, granting resources, and banning malicious users.
38
 
39
---
40
 
41
## 🎮 How to Play
42
 
43
1. **Watch it Grow** — Sparks automatically fly toward the Heart Crystal. Every hit generates Energy.
44
2. **Upgrade** — Spend Energy on more Sparks, faster Speed, higher Power, or better Crit chance.
45
3. **Set a Name** — Click **"Set Name"** to claim your spot on the live Leaderboard.
46
4. **Ascend** — Once you hit **1 Million Energy**, reset your run for Ascension Points and a permanent boost.
47
48
---
49
 
50
## 🛠️ Tech Stack
51
 
52
| Layer | Technology |
53
|---|---|
54
| Frontend | HTML5, Vanilla JavaScript (ES6 Modules) |
55
| Styling | Tailwind CSS (via CDN) |
56
| Backend / DB | Firebase (Anonymous Auth + Firestore) |
57
| Rendering | HTML5 `<canvas>` API |
58
 
59
---
60
 
61
## 🚀 Setup & Self-Hosting
62
 
63
Zen Sparks uses Firebase for its real-time leaderboard and multiplayer features. You'll need your own Firebase project to run it.
64
 
65
### 1. Clone the repo
66
```bash
67
git clone https://github.com/yourusername/zen-sparks.git
68
```
69
 
70
### 2. Create a Firebase Project
71
1. Go to the [Firebase Console](https://console.firebase.google.com/)
72
2. Create a new project
73
3. Enable **Firestore Database** *(start in production mode)*
74
4. Enable **Authentication** → turn on **Anonymous** sign-in
75
76
### 3. Set Firestore Security Rules
77
```
78
rules_version = '2';
79
service cloud.firestore {
80
  match /databases/{database}/documents {
81
    match /players/{userId} {
82
      allow read: if true;
83
      allow write: if request.auth != null && request.auth.uid == userId;
84
    }
85
  }
86
}
87
```
88
 
89
### 4. Configure the App
90
When you first load `index.html`, the game will prompt you to paste your **Firebase Configuration object**. You can find this in your Firebase Project Settings under **Web App**.
91
 
92
---
93
 
94
## 📄 License
95
 
96
This project is open source. Feel free to fork, remix, and build on it!
