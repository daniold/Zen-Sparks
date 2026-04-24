🎇 Zen Sparks - Idle Game

Zen Sparks is a relaxing, visually satisfying HTML5 canvas idle game where players generate energy by managing "Sparks" that orbit and collide with a central Heart Crystal. Grow your energy, upgrade your sparks, climb the global leaderboard, and ascend to gain permanent multipliers!

✨ Features

Mesmerizing Canvas Graphics: Smooth, particle-based animations rendered on an HTML5 Canvas.

Idle & Offline Progress: Keep earning energy even when you close the tab. The game calculates your offline earnings the next time you log in!

Upgrades & Progression: * Sparks: Buy more sparks to increase hit frequency.

Power: Increase the base energy generated per hit.

Speed: Make your sparks fly faster.

Crit %: Chance to land a critical hit for 5x energy!

Ascension System (Prestige): Reset your progress in exchange for Ascension Points (AP), granting a permanent global multiplier to all future energy gains.

Global Leaderboard: Real-time top 50 leaderboard powered by Firebase Firestore. See your exact rank among all players!

Player Interaction: Gift energy to other players, completely anonymously if you choose.

Custom Themes: Change the visual style of the game (Default, Spooky Halloween, Winter Holiday).

Admin Dashboard: Built-in developer console and dashboard to manage players, monitor live stats, grant resources, and ban malicious users.

🎮 How to Play

Watch it Grow: Sparks automatically fly towards the center crystal. Every hit generates Energy.

Upgrade: Use your Energy to buy more Sparks, increase their Speed, boost their Power, or raise your Critical Hit chance.

Set a Name: Click "Set Name" at the top to secure your spot on the live Leaderboard.

Ascend: Once you hit 1 Million Energy, you can Ascend. This resets your current run but gives you Ascension Points (AP) to speed up your next run.

🛠️ Tech Stack

Frontend: HTML5, Vanilla JavaScript (ES6 Modules)

Styling: Tailwind CSS (via CDN)

Backend / Database: Firebase (Anonymous Authentication & Firestore)

Rendering: HTML5 <canvas> API

🚀 Setup & Installation (Self-Hosting)

Because Zen Sparks uses Firebase for its real-time leaderboard and multiplayer features, you will need to set up your own Firebase project if you fork this repository.

Clone the repo:

git clone [https://github.com/yourusername/zen-sparks.git](https://github.com/yourusername/zen-sparks.git)


Create a Firebase Project:

Go to the Firebase Console.

Create a new project.

Enable Firestore Database (Start in production mode).

Enable Authentication (Turn on "Anonymous" sign-in).

Firestore Rules:
Set your Firestore rules to allow read/write access to the players collection:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /players/{userId} {
      allow read: if true;
      allow write: if request.auth != null && request.auth.uid == userId;
    }
  }
}


Configure the App:
When you first load index.html in your browser, the game will prompt you to paste your Firebase Configuration object. You can find this in your Firebase Project Settings under "Web App".
