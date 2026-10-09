# Cue Light

Click track, spoken section cues and setlists for worship teams. Everything is plain static files: no build step, no server code.

## Files

- `index.html` - the whole app
- `sw.js` - offline support (caches the app after the first visit)
- `manifest.webmanifest` + `icons/` - lets phones install it like an app
- `fonts/` - self-hosted fonts, so it looks right with no internet

Keep the folder structure as it is.

## Deploy to GitHub Pages

1. Create a new repository (for example `cue-light`).
2. Upload everything in this folder to the root of the repository.
3. Go to Settings, then Pages. Under "Build and deployment", choose "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. After a minute your app is live at `https://<your-username>.github.io/cue-light/`.

## Deploy to Netlify (no Git)

1. Go to app.netlify.com/drop.
2. Drag this whole folder onto the page. You get a live URL immediately.

## Move your songs from the Claude version

1. Open the old Cue Light link in Claude, switch to Edit, and press Export backup.
2. Open your new site, switch to Edit, press Import backup and choose that file.

Import merges: songs and setlists in the file are added, and ones that already exist are replaced by the file's version.

## Install on a phone

- iPhone/iPad: open the site in Safari, tap Share, then Add to Home Screen.
- Android: open it in Chrome, tap the menu, then Install app.

Open it once while online. After that it works without internet.

## Updating the app

When you upload a new `index.html`, also change `CACHE_VERSION` in `sw.js` (for example `cuelight-v2`). Devices pick up the new version the next time they open the app online.

## Good to know

- Songs are stored on each device separately. Export a backup regularly, and use Import to copy songs to another device.
- On iPhone, locking the screen or switching apps stops the audio. Keep the screen on while playing (the app asks the phone to stay awake, but test this on your device).
