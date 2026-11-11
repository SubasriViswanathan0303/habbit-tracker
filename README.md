# Couple Habit Tracker

Monday–Sunday habit tracker for two (Subu & Hubby) with day/week/month views, Silver/Gold/Platinum weekly awards, custom habits, background photos and optional multi-device sync.

## 1. Publish on GitHub Pages

1. Create a public repository on GitHub (e.g. `habit-tracker`).
2. Upload `index.html` and `README.md` (Add file → Upload files → Commit).
3. **Settings → Pages** → Source: *Deploy from a branch* → branch `main`, folder `/ (root)` → Save.
4. After a minute it is live at `https://<your-username>.github.io/habit-tracker/`.

On each phone, open the link and choose **Add to Home Screen**.

## 2. Save and share across devices (one-time, ~5 minutes, free)

GitHub Pages can only host the page, so a free Firebase Realtime Database keeps your ticks. Without it, ticks stay on one device.

1. Go to https://console.firebase.google.com and sign in with a Google account.
2. **Create a project** (any name, turn Google Analytics off).
3. Left menu → **Build → Realtime Database → Create Database**. Pick any location, start in **locked mode**.
4. Open the **Rules** tab, replace everything with the rules below, then **Publish**:

```json
{
  "rules": {
    "couples": {
      "$code": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

These rules let only someone who knows your long secret couple code read or write your data; nobody can list the database.

5. On the **Data** tab, copy the database address at the top. It looks like
   `https://your-project-default-rtdb.asia-southeast1.firebasedatabase.app`
6. Open your tracker → tap **☁️ Sync off – tap to set up** at the top → paste the address → leave the couple code empty → **Connect**.
7. Tap **Copy link** and send that link to your husband (and open it on your other devices). Opening it connects the device automatically.

From then on, ticks, habits, names and photos update live on all connected devices. Ticks made while offline are sent when the connection returns.

**Keep the link private.** Anyone who has it can see and edit your tracker.

## Background photos

On the Subu tab tap **📷 Set photo** for your picture, on the Hubby tab for his, and on the 💑 Together tab for your couple picture. Photos are shrunk automatically and also sync to other devices.

## Backup

Customize habits → **Export backup** saves everything to a file, and **Import backup** restores it.
