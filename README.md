# Common Pace Pilot

A clickable prototype of Common Pace, an endurance sponsorship marketplace, set up for usability testing.
Testers open the start page, pick a side (athlete or business), and work through short tasks on a phone or a computer.

**This is a prototype.** All names and numbers are sample data. There is no backend: nothing a tester types is saved or sent, and no email or payment is real.

## Put it online with GitHub Pages

1. Create a new repository on GitHub (for example `common-pace-pilot`).
2. Upload everything in this folder to the root of the repository, including the hidden `.nojekyll` file.
   - In the browser: **Add file → Upload files**, drag the files in, then **Commit changes**.
   - Or from a terminal:
     ```
     git init
     git add .
     git commit -m "Common Pace pilot"
     git branch -M main
     git remote add origin https://github.com/<your-account>/common-pace-pilot.git
     git push -u origin main
     ```
3. In the repository, go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick **main** and **/ (root)**, then **Save**.
4. After a minute or two, the page shows your site address, usually `https://<your-account>.github.io/common-pace-pilot/`. Send that link to testers.

Testers don't need an account. Anyone with the link can open it, so share it only with people you want testing.
GitHub Pages sites are public even when the repository is private (unless you're on GitHub Enterprise Cloud).

## Collect feedback

Open `index.html` and find this line near the top of the script:

```js
const FEEDBACK_URL = '';
```

Paste a link to a feedback form between the quotes (Google Forms, Typeform, Tally or similar) and commit the change.
Each task then gets a **Send feedback** button, and tapping **I got stuck** opens the form.
With the line left empty, testers are asked to tell whoever invited them.

The **It worked / I got stuck** ticks are kept only in each tester's own browser. Use the form to see results.

## What's in the folder

| File | What it is |
| --- | --- |
| `index.html` | Start page with the tester tasks |
| `App*.dc.html` | Phone app screens (shown in a phone-sized frame on computers) |
| other `*.dc.html` | Website screens |
| `TopNav.dc.html`, `AppTabs.dc.html` | Shared navigation used by the screens |
| `support.js` | Runtime that renders the screens; loads React from cdn.jsdelivr.net |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

Every screen has a **Test tasks** button that returns to the start page.

## Try it on your computer first

The screens need to be served over HTTP; opening `index.html` straight from the folder won't load them. From this folder:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.
