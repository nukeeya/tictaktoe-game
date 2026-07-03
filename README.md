

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
