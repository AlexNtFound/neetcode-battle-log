**English** | [简体中文](./README.zh-CN.md)

# 10-Week Battle Log

A single-file, no-build, opinionated **interview prep tracker** designed for a 10-week sprint. Originally built for a robotics/AI engineer prepping for top-tier US tech interviews (NVIDIA, Apple, Google, etc), but the framework works for any 10-week interview push.

> Stop choosing. Start doing. — the whole point of this tool.

## What it does

Open `index.html`, get hit with:

- **Today's focus** — auto-derived from the date: which phase you're in, what to do today, whether you should be applying yet
- **Recommended LeetCode problems** — next 2 unsolved from the NeetCode 150, filtered by your current phase's pattern focus (Phase 1 = Arrays & Hashing / Two Pointers / Sliding Window, etc)
- **Daily + weekly checklists** — phase-specific, persist per day
- **Cumulative counters** — LC problems, applications sent (practice / target), mocks done
- **NeetCode 150 roadmap** — all 150 problems with LC + NC solution links, dependency diagram, filterable by difficulty
- **Phase timeline** — visual where you are in the 10-week sprint
- **Key date countdown** — "X days until you start applying to dream companies"
- **Day-1 / phase-transition special actions** — auto-show "do these five things now" guidance on critical days
- **Bilingual (中文 / English)** — toggle language at the bottom; auto-detects browser language on first load
- **First-visit tutorial** — interactive walkthrough that picks your language, sets your start date, and spotlights each feature; re-runnable from Settings

## How to use

**Quickest path:**

1. Download `index.html` (single file, no dependencies)
2. Open it in any modern browser
3. Click **⚙ Settings** at the bottom to set your own start date
4. Bookmark it. Open it every day.

**Host it for yourself or share with friends:**

1. Fork this repo (or copy `index.html` into your own)
2. Settings → Pages → deploy from main branch
3. Visit `https://<your-username>.github.io/<repo-name>/`

Each visitor's data is stored in **their own browser's localStorage** — completely private, never sent anywhere, no account needed.

## Configuration

Everything lives in `index.html`. The plan is a JavaScript object at the top of the `<script>` tag — search for `PHASE_CONFIGS` to customize phase names, focus, daily tasks, and validation checkpoints.

Each phase is 14 days. Five phases. 70 days total. To change those numbers, edit `buildPhases()`.

## Storage backends

The tracker auto-detects its environment:

| Where you run it | Backend used |
|---|---|
| Claude.ai artifact | `window.storage` (persists across Claude sessions) |
| Anywhere else (file, GitHub Pages, your own server) | Browser `localStorage` (persists per browser, per origin) |

All keys are prefixed with `battlelog:` in localStorage. To wipe, click **⟲ reset all data** at the bottom.

## Stack

Pure HTML, CSS, and vanilla JavaScript. No build step. No npm. No frameworks. One file.

Fonts via Google Fonts CDN:
- Instrument Serif (display)
- Noto Serif SC (Chinese display)
- JetBrains Mono (body / data)

## Project structure

```
battle-log/
├── index.html        # The whole app — open this
├── README.md         # You are here
├── README.zh-CN.md   # 中文版
├── LICENSE           # MIT
└── .gitignore
```

That's it. No `src/`, no `dist/`, no `node_modules/`. The file you ship is the file you edit.

## Credit

The 150-problem roadmap is from [NeetCode](https://neetcode.io/roadmap) — links go to the original LeetCode problems and NeetCode video solutions. This tracker doesn't host any problem content; it's a thin organizational layer on top.

## Author

Built by **Alex Nan** — [github.com/AlexNtFound](https://github.com/AlexNtFound).

If you fork or redistribute, please preserve the copyright notice in `LICENSE` and the banner comment at the top of `index.html`.

## License

MIT — see [LICENSE](./LICENSE). Copyright (c) 2026 Alex Nan.
