[README.md](https://github.com/user-attachments/files/29642982/README.md)
# 💕 Tic-Tac-Toe — Live Multiplayer

A real-time Tic-Tac-Toe game you can host on GitHub Pages and play with someone far away.

---

## How it works

- One player creates a game → gets a shareable link
- The other player opens the link and joins
- Firebase keeps the board in sync in real-time — no server needed

---

## Setup (takes ~10 minutes)

### Step 1 — Create a free Firebase project

1. Go to **https://console.firebase.google.com**
2. Click **"Add project"** → give it any name → click through the steps
3. Once inside the project, click **"Realtime Database"** in the left sidebar
4. Click **"Create Database"** → choose **"Start in test mode"** → pick any location → Done

### Step 2 — Get your Firebase config

1. Click the ⚙️ gear icon → **"Project settings"**
2. Scroll down to **"Your apps"** → click the **`</>`** (Web) icon
3. Register the app (any nickname) → copy the `firebaseConfig` object

### Step 3 — Paste config into the game

Open `index.html` and find this section near the bottom:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  ...
};
```

Replace everything inside with your actual values from Firebase.

### Step 4 — Host on GitHub Pages

1. Create a new repo on GitHub (can be private or public)
2. Upload `index.html` to the repo
3. Go to **Settings → Pages → Source: Deploy from branch → `main` / `root`**
4. GitHub gives you a URL like: `https://yourusername.github.io/your-repo/`

That's your game link! Share it with your girlfriend so she can join.

---

## How to play

1. **You** open the game → enter your name → click "Create a new game"
2. A shareable link appears — send it to her
3. **She** opens the link → enters her name → clicks "Join game"
4. You're both in! Take turns clicking squares
5. First to get 3 in a row wins 🎉
6. After a game ends, both players can vote "Play again" to restart

---

## Firebase security (optional but recommended)

After testing, go to Firebase → Realtime Database → Rules and update to:

```json
{
  "rules": {
    "rooms": {
      "$roomId": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

This is already what "test mode" sets. For a private game between just two people, this is totally fine.

---

Built with ❤️ using Firebase Realtime Database + vanilla HTML/JS
