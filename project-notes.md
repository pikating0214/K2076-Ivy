# Letter Y Sound Quest Project Notes

## Project

Letter Y Sound Quest is a parent-facing and classroom-friendly static HTML game for Unit 6 Letter Y and the story theme In the Yard.

The page is designed for 4-6 year old children who may not be able to read directions independently yet.

## Learning Goals

- Recognize uppercase `Y` and lowercase `y`.
- Identify the Letter Y sound in a short text.
- Match the Y sound with words and distinguish it from the J sound.
- Identify words with the Y sound, including `yoyo`, `yard`, `yummy`, `yogurt`, and `yarn`.
- Review sight words: `got` and `ate`.

## Important Teaching Decisions

- The page is fully in English.
- The page should work on common devices, including desktop, iPhone, iPad, and Android phones/tablets.
- Each question has a `Listen` button and a complete spoken direction.
- Audio reads only the direction/question. Answer choices do not play audio.
- The page uses only `window.speechSynthesis`.
- Voice priority: `Samantha`, `Karen`, then `Google US English`, followed by another available English voice.
- The speech rate is `0.84`, pitch is `1.05`, and volume is `1`.
- The page does not show phonetic symbols to children.
- The final screen shows the raw score and a 5-star rating.

## File Structure

```text
K2176-Ivy/
├── index.html
├── project-notes.md
├── AGENTS.md
├── README.md
├── netlify.toml
└── assets/
    └── letter-y/
        └── lesson images
```

## Game Structure

The game has 19 questions.

### Level 1: Meet Letter Y

- Find uppercase `Y`
- Find lowercase `y`
- Recognize a Y word and a sentence containing Y

### Level 2: Y Sound Word Hunt

- Practice `yard`, `yummy`, `yogurt`, and `yarn`
- Identify words that begin with the Y sound

### Level 3: Listen and Compare

- Compare the Y sound with the J sound through real words
- Identify where the Y sound appears in `yoyo`
- Do not use fake phonetic spellings

### Level 4: In the Yard Picture Story

- Use approved lesson pictures from `assets/letter-y/`
- Practice:
  - `Yuki got a yellow yoyo.`
  - `Yuki ate the yogurt in the yard.`

### Level 5: Y Word Listening Challenge

- Listen to complete directions for Y-starting CVC words.
- Choose the correct word from meaningful Y words: `yak`, `yam`, `yes`, `yet`, and `yap`.
- Repeat the target CVC word three times for clearer listening, using complete directions such as `Listen carefully. Choose the word yak. Yak. Yak.`

## Lesson Images

The page uses images copied from:

```text
/Users/miaomiaopeng/Desktop/letter Y
```

Project copies are stored in:

```text
assets/letter-y/
```

The HTML currently displays clean, watermark-free versions of:

```text
story-yellow-yoyo.png
story-ate-yogurt.png
```

The other approved images remain available in `assets/letter-y/` for future revisions.

## Android Audio Compatibility

- Use only `window.speechSynthesis`; do not add APIs or generated audio unless explicitly requested.
- Every `Listen` button uses a complete English direction rather than a single short sound or word.
- The page waits briefly for Android Chrome to load speech voices.
- The page calls `speechSynthesis.resume()` when a child taps `Listen`.
- The page waits briefly after `speechSynthesis.cancel()` before speaking again.
- If an Android browser does not start speech, the page displays: `No sound? Please open this page in Chrome and tap Listen again.`
- Some Android WeChat or enterprise-app built-in browsers do not fully support browser speech synthesis. For reliable use, parents should open the page in Chrome.

## Privacy

This page does not collect or store names, scores, photos, or contact information.

## How To Test

1. Open `index.html`.
2. Confirm the title is Letter Y Sound Quest.
3. Confirm all 19 questions display correctly.
4. Click every `Listen` button and confirm each one reads a complete direction.
5. Confirm Level 4 displays the two lesson pictures.
6. Check the final score and 5-star panel.
7. Test on Android Chrome if possible.
8. If testing from WeChat, also choose Open in Browser and test in Chrome.

## Publishing

The teacher manually uploads or pushes changes through GitHub Desktop.

Do not push or trigger a deploy automatically.

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
