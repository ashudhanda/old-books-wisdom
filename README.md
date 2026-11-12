# Old Books Wisdom

Ancient wisdom on the **mind, focus, consistency, and perseverance** — 30 verified teachings from 13 classic books (Bhagavad Gita, Yoga Sutras, Dhammapada, Meditations, Tao Te Ching, Aristotle, Seneca, Chanakya, Sun Tzu, Thirukkural and more), organized by theme, with Hinglish explanations and student takeaways.

Includes a **truth-check section** exposing 32 famous-but-misattributed quotes with their real origins — nothing changed, nothing hidden.

**Live:** https://ashudhanda.github.io/old-books-wisdom/

Built with research-backed, source-traced passages. Every teaching carries its exact source (book, chapter/verse/sutra number).

## How it works

The whole site is a single `index.html` — no build step, no dependencies.

- **Library:** the 30 teachings are grouped into five themes (Mind, Focus, Consistency, Distraction, Failure — six each) and filtered with the theme buttons.
- **Search:** matches across the book, the quote, the student takeaway, the translation note, the named source, and the Hinglish explanation, so a Hinglish word finds its card too — accents are ignored, so “Muller” finds “Müller”.
- **Truth-check:** the 32 doubtful attributions are labelled Paraphrase, Fake, Unverified, Unknown, Disputed, Modern, Not a verse, Not translation, or Wrong author, each with the reason it fails the source check and a source link where one exists.

## Data shape

Each teaching in `index.html` is one object in the `items` array:

- `t` — theme key: `mind`, `focus`, `habit`, `desire`, or `failure`
- `book` — book plus location, e.g. `Bhagavad Gita 2.47`
- `q` — the source-traced quotation
- `take` — the student takeaway in plain English
- `src` / `url` — named translation or edition, plus its source link (no `url` when there is no link)
- `note` — optional translation note, shown under the takeaway

Every teaching also needs a Hinglish line in the `hinglish` map, keyed by `book` — except the second William James Ch. IV item, which `getHinglish` special-cases because both items share one book key. Truth-check entries live in the `myths` array as `[status, quote, reason, source-link]`.
