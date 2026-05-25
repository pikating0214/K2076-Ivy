# Letter X Sound Quest Project Notes

## Project

Letter X Sound Quest is a parent-facing and classroom-friendly HTML game for K2 DR Unit 6 Letter X, Lesson 109-110.

The page is designed for 4-6 year old children who may not be able to read directions independently yet.

## Learning Goals

- Recognize uppercase `X` and lowercase `x`.
- Hear and identify the Letter X sound through words.
- Identify words with the X sound, such as `box`, `fox`, `ox`, and `Max`.
- Notice that the X sound is different from the Q sound.
- Practice sight words from the lesson: `came`, `after`, `ran`, `down`.
- Review sight words: `with`, `an`.
- Review story meaning from `A Box`.

## Important Teaching Decisions

- The page is fully in English.
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
k2-letter-x-game/
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

The game has 16 questions.

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

## Scoring

- Total score: 16
- Each correct answer gives 1 star.
- Score updates immediately after a child clicks an option.
- The `Finish and See Score` button shows the final score panel.
- The final score panel shows the raw score and a 5-star rating.
- The final score panel includes a simple cartoon face and child-friendly English encouragement.

Score feedback:

- 14-16: strong performance, 4-5 stars
- 10-13: good progress, about 3-4 stars
- 0-9: needs more practice, about 0-3 stars

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
k2-letter-x-game/index.html
```

The page can be opened by double-clicking `index.html`.

## How To Test

1. Open `index.html`.
2. Click several `Listen` buttons.
3. Confirm the audio reads only the question direction.
4. Click answer choices.
5. Confirm answer choices do not play audio.
6. Click `Finish and See Score`.
7. Confirm the final score appears.

## How To Share

After teacher approval, this folder can be uploaded to a GitHub repository connected to Netlify.

Recommended publishing workflow:

1. Edit locally.
2. Preview and test locally.
3. Show the teacher what changed.
4. Wait for teacher confirmation.
5. Commit changes.
6. Push to GitHub.
7. Let Netlify auto-deploy.

## Future Improvements

- Add teacher-controlled option audio for selected questions.
- Add picture-based choices for non-readers.
- Add a replay story section for `A Box`.
- Add printable teacher answer notes separate from the student page.
- Add a parent message template explaining the learning goals.
