# IELTS Quest: Reading Realm — Version 4

A static HTML/CSS/JavaScript IELTS Reading practice game. No API key or paid service is required. It is an independent practice project and is not affiliated with IELTS or its test providers.

## What is included

- Academic and General Training full-length practice tests: 40 questions each, 60 minutes, raw score out of 40. These are original practice materials, not official IELTS tests.
- Vocabulary Village JSON packs with six additional original passages and 30 questions.
- JSON manifest (`content/manifest.json`) so the hosted app loads the listed content packs automatically.
- Manage Content import/export for adding your own JSON files.
- Progress, XP, completed passages and mistakes are saved in the current browser on the current device.
- The “Mixed practice” home button has been removed; the main action is “Start a mission.”

## Upload to GitHub and deploy

1. Upload the contents of this project folder to your GitHub repository, keeping `index.html`, `app.js`, `styles.css`, and the entire `content/` folder.
2. Make sure `content/manifest.json` and every file named in its `files` array are committed.
3. In Netlify, import the GitHub repository. For this plain static site, use no build command and set the publish directory to `.` if the files are at the repository root.
4. Netlify will serve the JSON packs; the app fetches them from `content/manifest.json` and loads them automatically. After adding another pack, add its filename to the manifest and commit both changes.

## Content files

- `content/academic-full-test-1.json` — Academic-style full test (40 questions).
- `content/general-training-full-test-1.json` — General Training-style full test (40 questions).
- `content/vocabulary-village-pack-1.json` and `content/vocabulary-village-pack-2.json` — extra Vocabulary Village passages and questions.
- `content/new-content-template.json` — template for making more original passages and questions.
- `content/manifest.json` — list of packs loaded automatically by the hosted app.

## Storage note

The app uses browser local storage, so progress remains after closing and reopening the page in the same browser on the same device. It does **not** create an online account or sync progress across different devices/browsers. Clearing site data can erase locally saved progress; use Export my content to back up custom JSON content.

## Adding a JSON pack

Create a JSON file with a top-level `passages` array and optional `tests` array. Give each passage a unique `id`. Add the new filename to `content/manifest.json` to load it automatically on the deployed website. You can also import a pack in Manage Content. A full-length test must contain exactly 40 questions and use a 60-minute timer.
