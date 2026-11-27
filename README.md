# NEON SNAKE 

A polished neon arcade Snake game built with HTML, CSS and vanilla JavaScript. No build step required; deploy directly to GitHub Pages.

## Features
- Responsive neon arcade UI, animated glow, particle bursts and sound effects
- Keyboard (Arrow keys / WASD), mobile touch D-pad and pause/resume
- Chill / Normal / Insane difficulty with progressive speed
- Score, personal best, timer, levels and local top-10 leaderboard
- Player profile and persistent scores via `localStorage`
- Optional shared online leaderboard powered by Supabase
- Reduced-motion-friendly, accessible controls and visibility auto-pause

## Run locally
Open `index.html` in a browser, or use a local static server:

```bash
python -m http.server 8000
```
Then visit http://localhost:8000.

## Deploy to GitHub Pages
1. Create a GitHub repository (for example `neon-snake`).
2. Upload all files in this folder to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`, then Save.
6. Your game will be published at `https://YOUR-USERNAME.github.io/neon-snake/`.

No GitHub Actions or build step required.

## Enable a shared online leaderboard (optional full-stack mode)
GitHub Pages hosts static files only. To make scores shared between all visitors, this project optionally connects to Supabase (free tier available).

1. Create a project at https://supabase.com/.
2. In the Supabase SQL Editor, run the contents of [`supabase/schema.sql`](supabase/schema.sql).
3. In `app.js`, set `SUPABASE_URL` and `SUPABASE_ANON_KEY` to your project's Project URL and anon/public key.
4. Commit and push. The app will automatically use the online leaderboard; if unavailable, it gracefully falls back to local scores.

The anon key is designed for browser use. Never put a Supabase `service_role` key in frontend code. The SQL policy permits public score inserts and public reads; add rate limiting / moderation for production leaderboards.

## Controls
| Action | Keys |
|---|---|
| Move | Arrow keys or WASD |
| Pause / resume | Space |
| Start / restart | Enter / on-screen button |
| Mobile | Touch D-pad |

## Project structure
```text
neon-snake/
├── index.html
├── styles.css
├── app.js
├── README.md
├── LICENSE
└── supabase/
    └── schema.sql
```

## Credits
Designed & built by **Farel Bayone Meijabar**.
