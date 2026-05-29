# Letter Q Sound Quest Project Notes

## Project

Letter Q Sound Quest is a parent-facing and classroom-friendly HTML game for K2 DR Unit 6 Letter Q and the story theme The Queen.

The page is designed for 4-6 year old children who may not be able to read directions independently yet.

## Learning Goals

- Recognize uppercase `Q` and lowercase `q`.
- Hear and identify the Letter Q sound in Q words.
- Understand that Q usually appears with `u` in words such as `queen`, `quiet`, `question`, `quilt`, `quail`, and `quarter`.
- Complete letter-sound matching for Q words.
- Listen to short English directions and choose the correct word, sentence, or letters.
- Practice sight words from the lesson: `saw`, `let`, `her`, and `for`.

## Important Teaching Decisions

- The page is fully in English.
- The page should work on common devices, including desktop, iPhone, iPad, and Android phones/tablets.
- The page does not show phonetic symbols such as `/kw/` to children.
- Children are expected to listen for the sound, not read phonetic symbols.
- Each question has a `Listen` button.
- Audio reads only the direction/question.
- Audio does not read the answer choices unless the teacher specifically asks for that later.
- The page uses only `window.speechSynthesis`.
- The page tries to choose the most natural English female voice available on the device.
- Voice priority: `Samantha`, `Karen`, then `Google US English`.
- The speech rate is set to `0.84`, which is slower but still natural.
- The pitch is set to `1.05`, which keeps the voice bright and teacher-friendly.
- Audio reads `Q sound` and `X sound` directly, matching the visible question text.
- Clicking an answer choice does not play audio.
- The final screen shows the total score and a 5-star rating.

## File Structure

```text
K2176-Ivy/
├── index.html
├── project-notes.md
├── AGENTS.md
├── README.md
└── netlify.toml
```

## Main Page

`index.html`

This is a single-file HTML game. It includes:

- HTML structure
- CSS styling
- JavaScript scoring logic
- Browser speech synthesis audio
- Final score display

No extra images, audio files, APIs, or JavaScript libraries are required.

## Game Structure

The game has 21 questions.

### Level 1: Meet Letter Q

Focus:

- Find uppercase `Q`
- Find lowercase `q`
- Recognize words/sentences connected to Letter Q

### Level 2: Q Sound Word Hunt

Focus:

- Identify words that start with the Q sound
- Practice `queen`, `quiet`, `quilt`, and `question`
- Keep correct answer positions mixed

### Level 3: Same or Different?

Focus:

- Listen for the Q sound
- Distinguish Q sound words from X sound words
- Identify where the Q sound appears in `queen`
- Keep correct answer positions mixed

### Level 4: Picture Word Match

Focus:

- Use simple built-in picture prompts to support meaning
- Practice `queen`, `quiet`, and `question`
- Use meaningful distractor words and sentences

### Level 5: Q Word Listening Challenge

Focus:

- Listen to complete directions for Q words.
- Choose the matching letters for `queen`, `quiet`, `quilt`, `quail`, and `quarter`.
- Each question has only one `qu` answer choice.
- Other answer choices are meaningful words, not fake words.
- Audio uses a complete direction such as `Choose the letters for queen.`

## Audio Behavior

The page uses the browser's built-in speech synthesis only.

Current audio settings:

```javascript
utterance.lang = "en-US";
utterance.rate = 0.84;
utterance.pitch = 1.05;
utterance.volume = 1;
```

The page loads the device's available voices with `window.speechSynthesis.getVoices()` and chooses voices in this order when available:

1. `Samantha`
2. `Karen`
3. `Google US English`
4. Other natural English female voices
5. Any available English voice

Each question has a `data-audio` direction. The `Listen` button reads only this direction.

Example:

```html
data-audio="Which word starts with the Q sound?"
```

Android compatibility notes:

- The page waits briefly for Android Chrome to load available speech voices before speaking.
- The page calls `speechSynthesis.resume()` after a child taps `Listen`, because some Android browsers pause the speech queue.
- The page avoids speaking immediately after `speechSynthesis.cancel()`; it waits a short moment so Android does not cancel the new audio by mistake.
- If the preferred female voices are not available on Android, the page falls back to another English voice on the device.
- The `Listen` button has a timeout fallback, so it returns to `Listen` even if Android does not fire the normal speech end event.
- For listening questions, do not use only one very short target word as the audio text. Use a complete direction such as `Choose the letters for queen.` so Android browsers can play the audio more reliably.

## Scoring

- Total score: 21
- Each correct answer gives 1 star.
- Score updates immediately after a child clicks an option.
- The `Finish and See Score` button shows the final score panel.
- The final score panel shows the raw score and a 5-star rating.
- The final score panel includes a simple cartoon face and child-friendly English encouragement.

Score feedback:

- 18-21: strong performance, 4-5 stars
- 13-17: good progress, about 3-4 stars
- 0-12: needs more practice, about 0-3 stars

## Privacy

This page does not collect:

- Student names
- Parent names
- Scores in a database
- Photos
- Contact information

Scores are only shown on the device screen and are not stored.

## How To Open Locally

Open this file in a browser:

```text
index.html
```

The page can be opened by double-clicking `index.html`.

## How To Test

1. Open `index.html`.
2. Click several `Listen` buttons.
3. Confirm every question has audio.
4. Confirm the audio reads only the question direction.
5. Click answer choices.
6. Confirm answer choices do not play audio.
7. In Level 4, confirm the picture prompts display on desktop and mobile.
8. In Level 5, click `Listen` and confirm the audio uses a complete direction.
9. Test on Android Chrome if possible: tap `Listen` once and confirm sound starts without needing a second tap.
10. Click `Finish and See Score`.
11. Confirm the final score appears.

## How To Share

After teacher approval, this repository can be uploaded to GitHub and served directly from GitHub Pages.

Recommended publishing workflow:

1. Edit locally.
2. Preview and test locally.
3. Ask Codex for upload steps if needed.
4. The teacher manually uploads or pushes to GitHub.
5. Let GitHub Pages publish the root `index.html`.

## GitHub Upload Notes

Final project folder:

```text
/Users/miaomiaopeng/Documents/GitHub/未命名/K2076-Ivy
```

Note: the local folder name may still be `K2076-Ivy` on this computer, but the GitHub repository name is `K2176-Ivy`.

GitHub Desktop local repository used for upload:

```text
/Users/miaomiaopeng/Documents/GitHub/未命名/K2076-Ivy
```

Target GitHub repository:

```text
https://github.com/pikating0214/K2176-Ivy
```

GitHub Pages site:

```text
https://pikating0214.github.io/K2176-Ivy/
```

GitHub Pages settings:

```text
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

Upload structure:

```text
K2176-Ivy/
├── index.html
├── project-notes.md
├── AGENTS.md
├── README.md
└── netlify.toml
```

Do not upload:

- `.DS_Store`
- old draft folders
- duplicate project folders
- API keys, tokens, or paid-service setup files

Important upload reminders:

- Use one upload workflow at a time.
- For this project, the teacher manually uploads or pushes to GitHub.
- Codex should provide steps only by default, not perform the final GitHub upload.
- If the teacher explicitly asks Codex to operate Git/Netlify, confirm the target repository and publishing impact first.
- GitHub Desktop is the recommended manual workflow.
- If a GitHub repository is created on the website with `README.md`, clone that repository first, then copy the final root files into the cloned repository.
- If GitHub Desktop shows `Publish branch`, check whether the local repository is connected to the correct GitHub remote.
- If GitHub Desktop shows `Push origin`, committed changes are ready to upload.
- If GitHub Pages shows an old page, try a hard refresh or add a temporary query string such as `?v=20260529`.
- If GitHub Pages shows `404`, check whether `index.html` is in the repository root and Pages is set to `main` / `/ (root)`.

Manual GitHub Desktop upload steps:

1. Open GitHub Desktop.
2. Select the local repository:

```text
/Users/miaomiaopeng/Documents/GitHub/未命名/K2076-Ivy
```

3. Check the changed files.
4. Write a short summary.
5. Click `Commit to main`.
6. Click `Push origin`.
7. Wait for GitHub Pages to publish.

## Future Improvements

- Add teacher-controlled option audio for selected questions.
- Add richer picture prompts if teacher provides approved images.
- Add a replay story section for The Queen.
- Add printable teacher answer notes separate from the student page.
- Add a parent message template explaining the learning goals.
