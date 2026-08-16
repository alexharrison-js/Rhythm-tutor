# Avartan — Indian Rhythm Trainer

A single-file, no-build web app for practicing Hindustani and Carnatic classical
percussion concepts: talas, layakari/gati subdivision, bols/solkattu, and
tihai/korvai phrase math. Built to run entirely client-side (Web Audio API),
so it works offline once loaded and needs no server or backend.

## Put it on GitHub Pages (~2 minutes)

1. Create a new repository on GitHub (any name, e.g. `avartan`).
2. Upload `index.html` to the root of that repository (drag-and-drop on
   github.com works fine — no git command line needed).
3. Go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`,
   branch `main`, folder `/ (root)`. Save.
5. GitHub will give you a URL like `https://yourusername.github.io/avartan/`.
   It can take a minute or two to go live the first time.
6. Open that URL on your iPhone in Safari. Optionally tap the Share icon →
   **Add to Home Screen** so it behaves like a standalone app.

That's it — one file, no dependencies to install, nothing to build.

## What's inside

- **Path** — a guided curriculum (8 modules, 26 lessons) that walks you
  through the whole app in a sensible order: foundations → even cycles →
  uneven cycles → subdivision → polyrhythm → bols/solkattu → tihai/korvai →
  synthesis. Tapping a lesson jumps you into the relevant practice tab with
  it pre-configured, plus a banner with the instruction and a
  "Complete & next" button. Progress is saved in the browser
  (`localStorage`), so it's there when you come back. A **Quick review**
  button runs a short, curated pass (~8 key ideas spanning every module) for
  spaced repetition without redoing the whole path, and tracks when you last
  reviewed and how many times.
- **Cycle** — pick a tala (Hindustani or Carnatic, plus a custom
  additive-grouping sandbox), see it as a rotating wheel with Sam/tali/khali
  color-coded, hear it, follow the scrolling bol/count notation.
- **Subdivide** — two sub-modes:
  - *Single beat*: subdivide a beat into 2/3/4/5/6/7/9 with the standard
    Carnatic counting syllables (Ta Ka Di Mi, Ta Ki Ta, etc.) as a visual +
    audio guide — the layakari/gati/nadai skill.
  - *Polyrhythm*: "A over B" cross-rhythms (3:2, 4:3, 5:4, 5:3, 7:4, 7:3,
    11:3, 11:4, or any custom ratio) — two evenly-spaced pulse streams
    sharing one cycle, scheduled from a single precise clock (via the
    LCM of the two counts) so they never drift apart, with independent
    color-coded rows and a sweeping cycle-progress bar.
- **Bols** — a tap-to-paint bol sequencer with presets (Teentaal, Ektaal,
  Rupak thekas, tisra/chatusra/misra solkattu drills), plus a tihai/korvai
  calculator that computes exactly where a three-times phrase needs to start
  so it lands on Sam.
- **Learn** — a filterable glossary of the concepts, each tagged by
  tradition, with a short note connecting it to jazz/improvisation vocabulary.

Manual practice (the four tabs above) and the guided Path are the same
underlying widgets — the Path just pre-configures and deep-links into them,
so nothing is duplicated and your progress/practice state stays consistent
either way you get there.

## Notes on scope and accuracy

Carnatic tala-keeping is traditionally done with claps/finger-counts/waves,
not fixed spoken syllables the way Hindustani theka works — the app shows
numeric counts for Carnatic cycles rather than inventing spoken "bols" for
them, and keeps konnakol/solkattu (which *is* syllable-based) as its own
layer in the Bols tab. A few groupings (e.g. Misra Chapu, Sankeerna gati) have
more than one traditional way to break down; the app picks one common,
defensible decomposition and says so.

Everything is intentionally *tradition-neutral where the underlying idea is
shared* (Sam, laya, vibhag/anga, additive rhythm) and tagged by tradition
where the practice actually diverges (khali, jaati, solkattu).
