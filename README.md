# Capability Coach — putting it on your iPhone

Five minutes, free, no Apple Developer account and no Mac required.
The result is a real icon on your home screen that opens full screen with no browser
bars, works on a plane with no signal, and speaks in one of Apple's own voices.

---

## Step 1 — Put the folder online

The app has to be served over `https` for the offline caching and the microphone to
work. GitHub Pages is free and takes about three minutes.

1. Go to **github.com** and sign in, or create an account.
2. Click **+** at the top right, then **New repository**.
3. Name it `coach`. Choose **Public**. Tick **Add a README file**. Click **Create repository**.
4. On the repository page click **Add file**, then **Upload files**.
5. Drag in every file from this folder: `index.html`, `manifest.webmanifest`, `sw.js`,
   `icon-180.png`, `icon-192.png`, `icon-512.png`, `icon-1024.png`.
6. Click **Commit changes**.
7. Click **Settings**, then **Pages** in the left sidebar.
8. Under *Branch*, choose **main** and **/ (root)**, then **Save**.
9. Wait about a minute, then refresh. GitHub shows the address, which will look like
   `https://YOURNAME.github.io/coach/`.

If a public repository is a concern — the app contains your full evidence file, your
figures, and the gaps — use a **private** repository instead and pick a different host.
The simplest private option is **Netlify Drop**: go to `app.netlify.com/drop`, drag this
whole folder onto the page, and it gives you an https address immediately without an
account. The address is unguessable but not password protected. For a password, sign in
to Netlify free and add **Site settings → Access control → Password protection**.

## Step 2 — Add it to your home screen

On your **iPhone or iPad**:

1. Open the address in **Safari**. It must be Safari — Chrome on iOS cannot install
   home screen apps.
2. Tap the **Share** button, the square with the arrow at the bottom of the screen.
3. Scroll down and tap **Add to Home Screen**.
4. Name it **Coach** and tap **Add**.

On your **Mac**:

1. Open the address in **Safari**.
2. Menu bar → **File** → **Add to Dock**.

You now have the icon. Open it once while online so it can cache itself, and after
that it runs with no connection.

## Step 3 — Choose your voice

The voice list in the coach controls comes from the voices installed on your device.
The default ones are adequate. The good ones are a free download and worth the two
minutes:

**Settings → Accessibility → Spoken Content → Voices → English → Australian**

Download **Karen (Premium)** or **Matilda (Enhanced or Premium)**. Then reopen the app
and pick the new voice from the dropdown in the coach controls. The difference between
the compact voice and the premium voice is considerable over a forty minute session.

## A few things worth knowing

**The microphone.** *Say it back* uses Safari's built-in dictation. The first time, iOS
asks for permission for both the microphone and speech recognition — allow both. On
iPhone this sends audio to Apple for transcription in the same way Siri dictation does.
If you would rather it did not, skip the microphone and tap the key facts manually as
you say each one; the exercise works either way.

**Speech stops when the screen locks.** That is an iOS rule, not a fault in the app.
For a long listening session, set **Settings → Display & Brightness → Auto-Lock** to
*Never* while you work, or keep tapping the screen.

**Your progress** — which segments you have heard — is stored on the device only.
Nothing leaves your phone. Clearing Safari data clears it.

**Updating it.** If a newer `index.html` is produced later, upload the new file over the
old one, then close and reopen the app twice. The service worker version is `coach-v1`
in `sw.js`; bumping that number to `coach-v2` forces the update immediately.

**Offline.** Everything is inside `index.html` — the whole evidence file, all 213
indicators, all 44 STARs and roughly four hours of coaching script. There is no server
call once it is cached, which is also why the file is large.
