# Selah — Sermon Notes & Bible

A responsive sermon notebook and Bible reader designed for GitHub Pages. Notes are saved in your browser and can be exported. Import a Bible text file you are legally allowed to use to browse and search it offline.

## Features
- Responsive two-panel notebook and Bible reader
- Sermon title, speaker, date, topic, main scripture and free-form notes
- Auto-save to browser storage, saved sermon list, copy notes, JSON backup export
- Book/chapter navigation and full-text search for imported verses
- Tap a verse to set the main scripture; double-click a verse (or click a search result) to insert it into notes
- Service worker caches the app shell for offline use after the first successful visit on GitHub Pages
- Bible text you import is stored locally in this browser

## Run it
1. Download/unzip this folder.
2. To use offline service-worker support, publish it to GitHub Pages (service workers require HTTPS or localhost).
3. Open the published Pages URL once while online. Then the app shell can load offline in that same browser/device.
4. Import your licensed Bible file from **Import Bible**.

Opening `index.html` directly from a file manager also lets you use the notebook and import Bible data in many browsers, but service-worker offline caching is not available from `file://`.

## Bible import formats

### JSON (recommended)
An array of verse objects:
```json
[
  {"book":"Genesis","chapter":1,"verse":1,"text":"Verse text here","translation":"NLT"},
  {"book":"Genesis","chapter":1,"verse":2,"text":"Next verse","translation":"NLT"}
]
```
The app also accepts a JSON object with a `verses` or `data` array.

### TXT / CSV-style text
One verse per line:
```text
# book|chapter|verse|text|translation
Genesis|1|1|Verse text here|NLT
Genesis|1|2|Next verse|NLT
John|3|16|Verse text here|NLT
```
Keep `|` characters in the verse text only if needed; they are accepted after the third separator.

## About the NLT
The New Living Translation is copyrighted. This repository does **not** include the complete NLT text. Obtain an authorized digital copy or license and import only text you are permitted to use. The included sample verses are from the public-domain King James Version (KJV), labelled as KJV. The sample is intentionally small; it is not a complete Bible.

## Notes and backups
Notes are stored in this browser's local storage, not automatically synced between devices. Use **Export notes** regularly. Clearing browser/site data can erase locally stored notes and imported verses.
