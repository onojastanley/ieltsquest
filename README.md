# IELTS Quest: Reading Realm

A free static IELTS Reading practice game. No API key, paid service, or registration is required. This is an independent practice project and is not affiliated with IELTS or its test providers.

## GitHub content folders

The website automatically loads JSON content listed in `content/manifest.json`. Included packs:

- `academic-full-test-1.json` — 40-question, 60-minute Academic Reading test.
- `general-training-full-test-1.json` — 40-question, 60-minute General Training Reading test.
- `vocabulary-village-starter.json` — vocabulary missions about context clues and paraphrasing.
- `vocabulary-village-advanced.json` — academic vocabulary mission.
- `new-content-template.json` — a template for creating more reading content.

These are original practice materials, not official IELTS test papers.

## Add more JSON packs through GitHub

1. Open your GitHub repository and open the `content` folder.
2. Upload your new `.json` file there, using a unique filename (for example `academic-full-test-2.json`).
3. Open `content/manifest.json` and add the filename to the `files` array. Keep commas and quotation marks valid JSON. Example: `"academic-full-test-2.json"`.
4. Commit the changes. Netlify will redeploy automatically if it is connected to your repository.
5. Reload the game. The new content will appear under its `pathway` value: `Academic`, `General Training`, or `Vocabulary Village`.

A browser cannot reliably discover arbitrary files in a static folder on its own, so the manifest is the list of content packs the app loads.

### JSON structure

Each pack should contain `passages` and optionally `tests`. Each passage requires a unique `id`, `title`, `intro`, `paras` array, and `qs` array. Every question needs `type`, `q`, `a`, `why`, and `ev`. Option-based questions also need `opts` and a zero-based integer answer index in `a`.

A test entry example:

```json
{
  "title": "Academic Full-Length Reading Practice Test 2",
  "pathway": "Academic",
  "durationMinutes": 60,
  "fullLength": true,
  "passageIds": ["topic-a-02", "topic-b-02", "topic-c-02"]
}
```

A full-length test must use 60 minutes and its passage questions must total exactly 40.

## No registration and saved progress

No account or email is required. XP, answers, achievements, completed passages, mistake notebook, and practice history are saved automatically in the browser's local storage. The data remains after closing or refreshing the page, but is limited to that browser/device. It will not sync across devices, and clearing browser storage may erase it. Export imported custom content from Manage Content if you need a backup.

## Publish to Netlify

Connect this GitHub repository to Netlify and set the publish directory to the project root (the folder containing `index.html`). Keep the `content/` folder and `content/manifest.json` in the deployed site. Future GitHub commits trigger a redeploy if continuous deployment is enabled.


## Full-length test structure

- Academic Reading: 40 questions across 3 detailed passages, 60 minutes.
- General Training Reading: 40 questions across 3 sections, 60 minutes.
- Each passage keeps four labelled paragraphs (A–D) so matching-information questions remain consistent. The texts have been expanded for more realistic sustained reading practice.
- Add future JSON content packs under `content/` and list their filenames in `content/manifest.json`.
- Learner progress is saved locally in the browser without registration; it does not automatically sync across devices.


### Full-length test standards

The included Academic test has three passages and 40 questions; the General Training test has three sections and 40 questions. Each reading text is approximately 700–900 words. Both full tests are timed for 60 minutes. After submitting, the results page displays the answer key with explanations and supporting evidence. These are original IELTS-style practice materials, not official IELTS papers.
