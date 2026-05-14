# taste-vision-song-contest
<!--
═══════════════════════════════════════════════════════════════════════
  TASTE-VISION SONG CONTEST — SETUP GUIDE
═══════════════════════════════════════════════════════════════════════

  This application requires a FREE Firebase account to enable
  real-time voting across multiple devices. Follow the steps below
  to connect your own database. Takes about 5 minutes.

  ── STEP 1: Create a Firebase project ─────────────────────────────
  1. Go to https://console.firebase.google.com
  2. Click "Add project"
  3. Give it a name (e.g. "my-song-contest")
  4. Click Continue → enable or disable Google Analytics as you prefer
  5. Click "Create project" and wait for it to finish

  ── STEP 2: Create a Realtime Database ────────────────────────────
  1. In the left sidebar click "Build" → "Realtime Database"
  2. Click "Create database"
  3. Choose your region (pick closest to your event location)
  4. Select "Start in test mode" → click "Enable"
  5. Your database is now live

  ── STEP 3: Get your Firebase config values ───────────────────────
  1. Click the ⚙ gear icon (top left) → "Project settings"
  2. Scroll down to "Your apps"
  3. Click the </> (Web) icon
  4. Enter any nickname (e.g. "contest-app") → click "Register app"
  5. Firebase shows you a config block — copy the values from it

  ── STEP 4: Fill in your values ───────────────────────────────────
  Search for "const FIREBASE_CONFIG" in this file (around line 820).
  Replace each empty string '' with the value from your Firebase
  config. Keep the quotes. Do NOT share this file publicly once
  your values are filled in — it contains your API credentials.

  ── STEP 5: Deploy ────────────────────────────────────────────────
  1. Save this file
  2. Go to https://app.netlify.com/drop
  3. Drag and drop this file onto the page
  4. Netlify gives you a public URL — share it with your voters!
  5. Show the QR code from the Host panel for easy mobile access

  ── SECURITY NOTE ─────────────────────────────────────────────────
  Your database starts in "test mode" which allows anyone with the
  URL to read and write. This is fine for a private event. After
  your event, go to Firebase Console → Realtime Database → Rules
  and set ".write" to false to lock it down.

  ── TROUBLESHOOTING ───────────────────────────────────────────────
  • "Voting Closed" on voter phones → make sure the host has clicked
    "Open Voting" in the Host Panel
  • Votes not syncing → check that databaseURL is filled in and that
    your Firebase project has Realtime Database enabled
  • App shows spinner indefinitely → your Firebase config has an
    error; double-check all values are copied correctly
  • Flags not showing → you need an internet connection for the
    first load; after that flags are cached by the browser

═══════════════════════════════════════════════════════════════════════
