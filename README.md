# Ponder

A single-page mental wellness companion for tracking mood, journaling, and finding mental health resources and crisis support.

🌐 **Live app:** [ponder-webapp.netlify.app](https://ponder-webapp.netlify.app/)

The whole app lives in one HTML file — open it in a browser and it works. No build step, no server, no install.

## Features

- **Mood Tracker** — log a daily mood with an optional note, view weekly averages, and browse past weeks filtered by week / month / year.
- **Diary** — a spiral-notebook style journal with an autosaved daily page and a grid of past entries to revisit.
- **Resources** — 14 cards covering common mental health topics (anxiety, depression, burnout, sleep, eating disorders, ADHD, OCD, PTSD, self-harm, loneliness, and more). Self-help tips are sourced from the NHS and UK mental health charities, with links to further reading.
- **Crisis Support** — searchable directory of free, confidential 24/7 helplines across 36 countries.
- **Sign in with Google** (via Firebase) to sync mood entries and diary pages across devices. Works as a guest too — entries just won't persist when the tab closes.

## Getting started

The easiest way: just visit [ponder-webapp.netlify.app](https://ponder-webapp.netlify.app/).

To run it locally, open `ponder_v9.html` in any modern browser — that's it. Or for a quick local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/ponder_v9.html
```

To deploy your own copy: the app is currently hosted on [Netlify](https://www.netlify.com/), but any static host (GitHub Pages, Vercel, Cloudflare Pages) works without configuration — just drop the HTML file in.

## Tech

- Plain HTML, CSS, and vanilla JavaScript — no framework, no bundler.
- [Firebase](https://firebase.google.com/) Authentication (Google sign-in) and Firestore for cloud sync.
- Google Fonts: Playfair Display, Manrope, Caveat, Kalam.

The Firebase config in the file is for a public demo project. If you fork this and want your own user data isolated, swap the `firebaseConfig` object near the top of the `<head>` for your own Firebase project's config and set up Firestore security rules.

## Project structure

```
ponder_v9.html    # the entire app — markup, styles, and script
README.md         # this file
```

The HTML file is heavily commented and organised into three parts:

1. `<head>` — fonts, Firebase setup, all CSS
2. `<body>` — the five sections (Home, Mood, Diary, Resources, Crisis)
3. `<script>` — auth, storage helpers, navigation, and the per-section logic

Search for `──` inside the `<script>` tag to jump between logical sections.

## A note on the content

The self-help tips in the Resources section are drawn from publicly available NHS and UK mental health charity guidance and are intended for general educational purposes only. They are **not** a substitute for professional medical advice. If you're struggling, please speak to a GP or qualified mental health professional. If you're in crisis, the Crisis Support section lists free helplines available 24/7.

## License

Add your preferred license here (MIT is a common choice for projects like this).

