# Letter X Sound Quest Project Notes

## Project

Letter X Sound Quest is a parent-facing and classroom-friendly HTML game for K2 DR Unit 6 Letter X, Lesson 109-110.

The page is designed for 4-6 year old children who may not be able to read directions independently yet.

## Learning Goals

- Recognize uppercase `X` and lowercase `x`.
- Hear and identify the Letter X sound through words.
- Identify words with the X sound, such as `box`, `fox`, `ox`, and `Max`.
- Listen to CVC or short X words and choose the matching letters, such as `f-o-x`, `b-o-x`, `s-a-x`, `t-a-x`, and `M-a-x`.
- Notice that the X sound is different from the Q sound.
- Practice sight words from the lesson: `came`, `after`, `ran`, `down`.
- Review sight words: `with`, `an`.
- Review story meaning from `A Box`.

## Important Teaching Decisions

- The page is fully in English.
- The page should work on common devices, including desktop, iPhone, iPad, and Android phones/tablets.
- The page does not show phonetic symbols such as `/ks/` or `/kw/`.
- Children are expected to listen for the sound, not read phonetic symbols.
- Each question has a `Listen` button.
- Audio reads only the direction/question.
- Audio does not read the answer choices unless the teacher specifically asks for that later.
- The page uses only `window.speechSynthesis`.
- The page tries to choose the most natural English female voice available on the device.
- Voice priority: `Samantha`, `Karen`, then `Google US English`.
- The speech rate is set to `0.84`, which is slower but still natural.
- The pitch is set to `1.05`, which keeps the voice bright and teacher-friendly.
- Audio reads `X sound` and `Q sound` directly, matching the visible question text.
- Clicking an answer choice does not play audio.
- The final screen shows the total score.

## File Structure

```text
K2176/
├── index.html
└── project-notes.md
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

### Level 1: Meet Letter X

Focus:

- Find uppercase `X`
- Find lowercase `x`
- Recognize words/sentences connected to Letter X

### Level 2: X Sound Word Hunt

Focus:

- Identify words with the X sound
- Practice `box`, `fox`, `ox`, and `Max`

### Level 3: Same or Different?

Focus:

- Listen for the X sound
- Distinguish X sound words from Q sound words
- Identify where the X sound appears in a word

### Level 4: Story Path

Focus:

- Practice sight words in simple story sentences
- Use `came`, `after`, `ran`, and `down`

### Level 5: X Word Listening Challenge

Focus:

- Listen to X words.
- Choose the matching letters for `fox`, `box`, `sax`, `tax`, and `Max`.
- Audio plays only the target word for each listening question.

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
data-audio="Listen. Which word has the X sound?"
```

Android compatibility notes:

- The page waits briefly for Android Chrome to load available speech voices before speaking.
- The page calls `speechSynthesis.resume()` after a child taps `Listen`, because some Android browsers pause the speech queue.
- The page avoids speaking immediately after `speechSynthesis.cancel()`; it waits a short moment so Android does not cancel the new audio by mistake.
- If the preferred female voices are not available on Android, the page falls back to another English voice on the device.
- The `Listen` button has a timeout fallback, so it returns to `Listen` even if Android does not fire the normal speech end event.
- For CVC listening questions, do not use only one very short target word as the audio text. Use a complete direction such as `Choose the letters for fox.` so Android browsers can play the audio more reliably.

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
K2176/index.html
```

The page can be opened by double-clicking `index.html`.

## How To Test

1. Open `index.html`.
2. Click several `Listen` buttons.
3. Confirm the audio reads only the question direction.
4. Click answer choices.
5. Confirm answer choices do not play audio.
6. In Level 5, click `Listen` and confirm the audio reads only the target word.
7. Test on Android Chrome if possible: tap `Listen` once and confirm sound starts without needing a second tap.
8. Click `Finish and See Score`.
9. Confirm the final score appears.

## How To Share

After teacher approval, this folder can be uploaded to a GitHub repository connected to Netlify.

Recommended publishing workflow:

1. Edit locally.
2. Preview and test locally.
3. Ask Codex for upload steps if needed.
4. The teacher manually uploads or pushes to GitHub.
5. Let Netlify auto-deploy after GitHub is updated.

## GitHub Upload Notes

Final project folder:

```text
/Users/miaomiaopeng/Documents/English teaching/K2176
```

GitHub Desktop local repository used for upload:

```text
/Users/miaomiaopeng/Documents/GitHub/未命名/K2076-Ivy
```

Target GitHub repository:

```text
https://github.com/pikating0214/K2076-Ivy
```

Netlify site:

```text
https://xgk2176-ivy.netlify.app/
```

Netlify build settings:

```text
Branch to deploy: main
Base directory: /
Build command: Not set
Publish directory: K2176
Config file: netlify.toml sets publish = "K2176"
```

Upload structure:

```text
K2176/
├── index.html
└── project-notes.md
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
- If a GitHub repository is created on the website with `README.md`, clone that repository first, then copy the final `K2176` folder into the cloned repository.
- If GitHub Desktop shows `Publish branch`, check whether the local repository is connected to the correct GitHub remote.
- If GitHub Desktop shows `Push origin`, committed changes are ready to upload.
- Be careful with similar repository names such as `K2076-lvy` and `K2076-Ivy`; lowercase `l` and uppercase `I` can look almost the same.
- If Netlify shows `Page not found`, check whether `Publish directory` is set to `K2176`.

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
7. Wait for Netlify to auto-deploy.

## Future Improvements

- Add teacher-controlled option audio for selected questions.
- Add picture-based choices for non-readers.
- Add a replay story section for `A Box`.
- Add printable teacher answer notes separate from the student page.
- Add a parent message template explaining the learning goals.
