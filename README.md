# Chinnu — Learn & Play 🐱🦁🧠

A voice-powered learning app for kids (ages 4–12) — one app, three connected games sharing a child profile and star count:

1. **Guess It!** — identify animals, birds, fruits & veggies by voice, with age-based difficulty and Hindi synonyms (hathi, gajar, baingan…)
2. **Talking Buddy** — Chinnu the cat repeats whatever the child says in a funny chipmunk voice
3. **GK Quiz** — easy spoken general-knowledge questions with big picture answers

The app asks the child's name and age once, greets them by name, tracks total stars and games played across all games, and remembers everything between visits (localStorage).

**Built with:** plain HTML/CSS/JS — no build step, no dependencies.
- Speech recognition: Web Speech API (`en-IN`)
- Speech output: `speechSynthesis`
- Fuzzy answer matching (typo/accent tolerant, synonyms, plurals)
- Tap-to-answer buttons as a fallback when no mic is available

---

## ▶️ Run locally

The mic needs a "secure context", so use localhost (not by double-clicking the file).

```bash
# from this folder — pick whichever you have installed:
python3 -m http.server 8000
# or
npx serve .
```

Then open **http://localhost:8000** in **Chrome** or **Edge** (best Web Speech API support). Allow microphone access when asked.

> Safari/Firefox: the game works, but voice recognition support is limited — the tap buttons will be used instead.

---

## 🌐 Put it online with GitHub Pages (free)

1. Create a new repository on GitHub (e.g. `guess-it-game`). Keep it **Public**.
2. Push this folder:

```bash
git init
git add .
git commit -m "Guess It! kids voice learning game"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/guess-it-game.git
git push -u origin main
```

3. On GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. Wait ~1 minute. Your game is live at:

```
https://YOUR_USERNAME.github.io/guess-it-game/
```

Share that link — it works on phones, tablets, and laptops. GitHub Pages serves over HTTPS, so the microphone works for everyone.

---

## 🎮 How to play

1. Choose an age band (4–6 / 7–9 / 10–12) — this sets the difficulty of items shown.
2. Pick a category: Animals, Birds, Fruits, Veggies, or Surprise Mix.
3. The game asks out loud: *"What animal is this?"*
4. Tap the mic 🎤 and say the answer — or tap one of the answer buttons.
5. Correct → praise + a star ⭐. Wrong → a gentle retry, then the game *teaches* the answer: *"This is a peacock. Can you say peacock?"*
6. 8 questions per round, spoken score at the end.

## 🛠️ Customizing

All the content lives in one place — the `BANK` object near the top of the `<script>` in `index.html`:

```js
{n:"elephant", e:"🐘", d:0, syn:["hathi"]}
//  name        emoji  difficulty(0/1/2)  accepted synonyms
```

Add items, more synonyms (any language), or whole new categories. `ROUND_LEN` controls questions per round.

## 📄 License

MIT — use it, remix it, build on it.
