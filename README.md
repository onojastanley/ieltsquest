# IELTS Quest: Reading Realm

A free, static IELTS Reading practice game made with HTML, CSS, and JavaScript. No API key or paid service is required. The project is independent and is not affiliated with IELTS or its test providers.

## Included JSON content packs

The `content` folder contains three importable files:

- `academic-full-test-1.json` — 3 original Academic-style passages, exactly 40 questions, and a 60-minute full-length practice test.
- `general-training-full-test-1.json` — 3 original General Training-style passages, exactly 40 questions, and a 60-minute full-length practice test.
- `new-content-template.json` — a starter template showing the supported question types and JSON structure.

These are original practice materials, not official IELTS passages. The reading topics, wording and questions are designed for practice; they do not reproduce an official IELTS paper.

## Import the two full-length tests

1. Open IELTS Quest and choose **Manage content** from the dashboard.
2. Choose **Choose a JSON file to import**.
3. Select `academic-full-test-1.json` from the `content` folder and then press **Import content**.
4. Repeat with `general-training-full-test-1.json`.
5. Scroll to **Launch a practice test** and choose either Academic or General Training. Each full-length test has 40 questions and a 60-minute timer.
6. During a full-length test, choose an answer and press **Save answer & next**. Use the numbered question buttons to move around. The test score is revealed at the end as a raw score out of 40, with answer explanations. This is not an official IELTS band score.

## Add more essays/passages and questions whenever you want

1. Make a copy of `new-content-template.json` and rename it, for example `climate-practice-pack-02.json`.
2. Give every new passage a unique `id` (for example `climate-change-02`). If you are creating a new test, its `passageIds` must match the passage IDs in the same file or passages already imported into this browser.
3. Replace the sample text, questions, answer keys, explanations and evidence with your own original content.
4. Save as `.json`, select it in **Manage content**, and choose **Import content**.
5. New passage IDs are added to the existing bank. Importing a passage with the same custom ID updates that passage. A test with the same title updates the existing test with that title.
6. Use **Export my content** regularly to back up all imported custom passages and tests.

Supported question formats include multiple choice, True/False/Not Given, Yes/No/Not Given, matching headings, matching information, matching features, sentence completion, summary completion, table completion, flow-chart completion and short answer. The game currently presents matching questions as one question at a time with options, rather than a whole matching grid.

### JSON structure

The top-level object contains `passages` and an optional `tests` array. Each passage needs a unique `id`, `title`, `intro`, a `paras` array and a `qs` array. Each question needs `type`, `q`, `a`, `why` and `ev`. Option-based questions use `opts` and an integer `a` giving the zero-based correct option index. For text-entry questions, `a` can be a string or an array of accepted answers.

A full-length test looks like this:

```json
{
  "title": "Academic Full-Length Reading Practice Test 2",
  "pathway": "Academic",
  "durationMinutes": 60,
  "fullLength": true,
  "passageIds": ["topic-a-02", "topic-b-02", "topic-c-02"]
}
```

All passages named in a full-length test must contain exactly 40 questions in total. Keep the timer at 60 minutes. Academic and General Training are separate pathways; create the test with the matching `pathway` value.

## Important storage note

Imported content is saved in the current browser on the current device. It does not automatically sync between your phone and computer, and clearing browser data may remove it. Export a backup before changing devices or clearing browser data. The files in the `content` folder are the source copies; importing them is what adds them to the game.

## Publish to Netlify

1. Sign in at https://app.netlify.com/.
2. Choose the manual deployment option.
3. Extract the ZIP and upload the website folder contents (`index.html`, `styles.css`, and `app.js`). Keep the `content` folder for your own JSON files, even though users import those files through the app.
4. Netlify provides your public website URL.
