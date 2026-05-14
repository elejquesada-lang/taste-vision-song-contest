# 🎤 Taste-Vision Song Contest
### A Eurovision-Style Voting App for Toastmasters Events
 
A free, open-source web application that brings the drama and excitement of Eurovision voting to your Toastmasters meetings, private events, or any group gathering. Each participant represents a country and members vote using the official Eurovision points system — 1, 3, 5, 8, 10, and 12 points. The results are revealed live with a dramatic animated scoreboard.
 
---
 
## ✨ Features
 
- **Eurovision scoring system** — 1, 3, 5, 8, 10 and 12 points per voter
- **Real-time sync** — votes appear instantly across all devices via Firebase
- **QR code sharing** — voters scan to open the ballot on their phone
- **Live reveal** — dramatic scoreboard that updates jury by jury
- **Anonymous voting** — hide voter names and show "Toastmaster 1, 2, 3..." instead
- **Drag-and-drop reordering** — host can rearrange countries in any order
- **World flags** — 197 country flags built in, with search by country name
- **Participant details** — add name and role below each country
- **Mobile-first** — fully responsive, designed for phone voting
- **Toastmasters branded** — includes the official shield logo and brand colours
---
 
## 📸 How It Works
 
| Role | What they do |
|---|---|
| **Host** | Sets up countries, opens voting, triggers the live reveal |
| **Voters** | Scan QR code on their phone, assign their 6 point values, submit |
| **Audience** | Watch the live scoreboard update dramatically during the reveal |
 
---
 
## 🚀 Quick Start — Run It Yourself
 
### Option A: Demo mode (no setup required)
1. Download `index.html` from this repository
2. Open it in any browser
3. Click **🎲 Demo** in the Host Panel to fill in random votes
4. Click **▶ Reveal** and enjoy the show
No internet connection required for demo mode. All votes stay in your browser's memory.
 
### Option B: Full real-time mode (Firebase required)
For multi-device voting where everyone's phone connects in real time, you need a free Firebase account. Follow the full setup guide below.
 
---
 
## 🔥 Firebase Setup Guide
 
This application requires a **free** Firebase account to enable real-time voting across multiple devices. The setup takes about 5 minutes.
 
### Step 1 — Create a Firebase project
 
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project**
3. Give it a name (e.g. `my-song-contest`)
4. Click Continue → enable or disable Google Analytics as you prefer
5. Click **Create project** and wait for it to finish
### Step 2 — Create a Realtime Database
 
1. In the left sidebar click **Build → Realtime Database**
2. Click **Create database**
3. Choose your region (pick the one closest to your event location)
4. Select **Start in test mode** → click **Enable**
5. Your database is now live
### Step 3 — Get your Firebase config values
 
1. Click the ⚙ gear icon (top left) → **Project settings**
2. Scroll down to **Your apps**
3. Click the `</>` (Web) icon
4. Enter any nickname (e.g. `contest-app`) → click **Register app**
5. Firebase shows you a config block — copy the values from it. It looks like this:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "my-project-12345.firebaseapp.com",
  databaseURL: "https://my-project-12345-default-rtdb.firebaseio.com",
  projectId: "my-project-12345",
  storageBucket: "my-project-12345.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef1234567890",
  measurementId: "G-XXXXXXXXXX"
};
```
 
### Step 4 — Fill in your values
 
1. Open `index.html` in any text editor (Notepad, TextEdit, VS Code)
2. Search for `const FIREBASE_CONFIG` (around line 820)
3. Replace each empty string `''` with the corresponding value from your Firebase config
4. Keep the quotes around each value
5. Save the file
> ⚠️ **Do not share this file publicly once your values are filled in** — it contains your API credentials. Only share the deployed URL, not the file itself.
 
### Step 5 — Deploy
 
1. Save the file
2. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
3. Drag and drop your `index.html` onto the page
4. Netlify gives you a public URL — share it with your voters!
5. Show the **QR code** from the Host panel for easy mobile access
---
 
## 🔐 Security Note
 
Your database starts in **test mode** which allows anyone with the URL to read and write. This is fine for a private event. After your event, lock it down:
 
1. Go to Firebase Console → Realtime Database → **Rules**
2. Replace the rules with:
```json
{
  "rules": {
    ".read": true,
    ".write": false
  }
}
```
 
---
 
## 🛠️ Troubleshooting
 
| Problem | Solution |
|---|---|
| "Voting Closed" on voter phones | Make sure the host has clicked **Open Voting** in the Host Panel |
| Votes not syncing across devices | Check that `databaseURL` is filled in and Realtime Database is enabled in Firebase |
| App shows spinner indefinitely | Your Firebase config has an error — double-check all values are copied correctly |
| Flags not showing | You need an internet connection for the first load; after that flags are cached |
| "Firebase not defined" error | Make sure your Firebase config values are all filled in, not empty strings |
 
---
 
## 🌐 Deploy for Free
 
The app is a single self-contained HTML file — no server, no build process, no dependencies to install.
 
**Netlify (recommended — 2 minutes):**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag `index.html` onto the page
3. Get a public URL instantly — share it or display the QR code
**GitHub Pages:**
1. Fork this repository
2. Go to Settings → Pages → Deploy from main branch
3. Your app is live at `https://yourusername.github.io/yourreponame`
---
 
## 📥 What to Download
 
> **Only download `index.html` — that is the entire application.**
> Ignore `README.md`, you are already reading it here on GitHub.
 
| File | What to do |
|---|---|
| ✅ `index.html` | **Download this** — it is the complete application |
| ❌ `README.md` | Ignore — this is just the guide you are reading right now |
| ❌ `eurovision-voting-TEMPLATE.html` | Ignore — this is an older version, do not use it |
 
**How to download `index.html`:**
1. Click on `index.html` in the file list above
2. Click the **Download raw file** button (⬇ icon, top right of the file view)
3. Save it to your computer
4. Open it in a browser to run the app, or follow the Firebase guide above to deploy it
---
 
## 🛠️ Built With
 
- **React 18** — UI components (loaded via CDN, no npm needed)
- **Firebase Realtime Database** — real-time vote sync across devices
- **Firebase Analytics** — optional usage tracking
- **QRCode.js** — QR code generation
- **Bebas Neue + Outfit** — typography
- Pure HTML/CSS/JS — no build tools, no frameworks, no installation
---
 
## 📄 Licence
 
Free to use, share, and modify for non-commercial purposes. If you improve it, consider sharing your changes back.
 
---
 
Built with ❤️ for the Toastmasters community.
