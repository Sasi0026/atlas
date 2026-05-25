# A.T.L.A.S.
### Adaptive Task, Learning & Achievement System

> A personal portfolio + growth operating system. Built to track who I am, what I'm building, and where I'm going — powered by **E.D.E.N.** (Evolving Developer Environment & Navigator), the AI layer inside ATLAS.

---

## What is ATLAS?

ATLAS is not just a portfolio. It is a **living proof-of-work system** — a daily driver that tracks every project, skill, blog entry, and goal I pursue as a developer. Instead of a static portfolio that says *"I know React"*, ATLAS shows 30 days of consistent learning, 7 blog entries on it, and a project shipped at the end.

Visitors — recruiters, collaborators, or fellow developers — see the **journey**, not just the destination.

---

## Project Structure

```
atlas/
├── frontend/                   # GitHub Pages — static site
│   ├── index.html              # Main entry point
│   ├── assets/
│   │   ├── css/
│   │   │   └── style.css
│   │   ├── js/
│   │   │   ├── app.js          # Core app logic
│   │   │   ├── tracker.js      # Task/skill/project tracker
│   │   │   ├── blog.js         # Blog log manager
│   │   │   └── eden.js         # EDEN AI integration
│   │   └── icons/
│   └── pages/
│       ├── dashboard.html
│       ├── projects.html
│       ├── skills.html
│       ├── goals.html
│       ├── blog.html
│       └── completed.html
│
├── backend/                    # FastAPI — deployed on Render
│   ├── main.py                 # FastAPI app entry point
│   ├── eden/
│   │   ├── router.py           # EDEN API routes
│   │   ├── agent.py            # EDEN AI logic (Groq + Llama 3)
│   │   └── context.py          # Builds EDEN's context from user data
│   ├── db/
│   │   ├── supabase.py         # Supabase client
│   │   └── models.py           # Data models
│   ├── api/
│   │   ├── projects.py
│   │   ├── skills.py
│   │   ├── goals.py
│   │   └── blogs.py
│   └── requirements.txt
│
├── README.md                   # This file
└── .gitignore
```

---

## Tech Stack

| Layer      | Technology              | Hosting         | 
|------------|-------------------------|-----------------|
| Frontend   | HTML, CSS, JavaScript   | GitHub Pages    | 
| Backend    | FastAPI (Python)        | Render          | 
| Database   | Supabase (PostgreSQL)   | Supabase Cloud  | 
| AI (EDEN)  | Groq API + Llama 3      | Via Render      | 

---

## Features

### 1. Task Manager (Core)

The heart of ATLAS. Everything I am working on lives here.

**Projects Tracker**
- Add a project with: title, description, tech stack, GitHub link, estimated days to complete, and importance level (High / Medium / Low)
- That many day-checkboxes appear in the progress bar — each checked day fills the bar
- High importance projects sort to the top automatically
- Missed days show visually so I know exactly when I stopped showing up
- On completion → project moves to the Completed Projects wall with GitHub link preserved

**Skills Tracker**
- Start a skill challenge: name, category, number of days (e.g. 30-day TypeScript challenge)
- Every day I show up → check the box → progress bar fills
- Missed days are visible — honest accountability
- On completion → skill is added to the Skills Badges / Achievement wall on the public portfolio

**Daily Goals**
- Add daily/weekly goals with priority (High / Medium / Low)
- Goals are sorted into priority buckets automatically
- Link a goal to a project or skill for context
- Check off when done — streak counter updates

**Blog Log**
- Log any concept, insight, or daily learning with a title, notes, topic tag, and type
- Quick popup ("Last 10 Blogs") shows the last 10 concept titles — so I always know where to pick up next
- Click any entry to read full notes
- Recently published entries shown on public portfolio page

---

### 2. Public Portfolio Pages

What the world sees when they visit my site.

**Projects Page**
- All completed projects displayed as cards
- Each card shows: project title, tech stack badges, 2–3 line overview, GitHub repo link
- Most recently completed projects appear at the top
- Visitors can click GitHub link to explore the actual code

**Skills & Achievements Wall**
- Completed skills displayed as achievement badges
- Game-inspired: each skill has a level and challenge completion status
- Small business / real-world problem challenges tied to each skill level — proves practical knowledge, not just tutorial completion
- Showcases to interviewers: I am a real-world problem solver, not just a course finisher

**Blog / Concepts Page**
- Recently published blog entries displayed publicly
- Each entry has a title, topic tag, date, and type (Concept / Project Note / Daily Learning / Insight)
- Visitors can read what I have been learning and thinking about

**About / Who I Am**
- Full bio, background, current interests (skills being learned, current project focus)
- What I am currently working on — updated live from ATLAS tracker data

---

### 3. EDEN — AI Navigator (Phase 2)

EDEN is the intelligence inside ATLAS. Think JARVIS inside Iron Man's suit.

**How it works:**
- I open ATLAS and say: *"Hey EDEN"*
- EDEN responds, knowing my full context — current project, streak, last blog, pending goals, missed days

**What EDEN knows:**
- Which project I am currently working on and how many days in
- My skill streak status — is it at risk of breaking?
- What concept I last blogged about
- Which goals I completed today and which I skipped
- My overall progress across everything

**What EDEN does:**
- Proactively nudges: *"You haven't touched TypeScript in 4 days — streak breaks tomorrow"*
- Suggests next steps: *"You've logged 3 system design entries — you're ready for the intermediate challenge"*
- Summarises progress on demand: *"Here's your week: 2 project days checked, 5 skill days logged, 1 blog entry"*
- Answers: *"What am I currently working on?"*, *"How far am I on the React project?"*

**Tech:**
- FastAPI backend on Render
- Groq API + Llama 3 (free, open source, fast)
- Context built fresh from Supabase data on every EDEN call

---

### 4. Gamification Layer (Phase 3)

Making growth feel like levelling up.

- Each skill has levels: Beginner → Intermediate → Advanced → Expert
- To unlock the next level, complete a real-world challenge tied to that skill
- Challenges are small business problems — not LeetCode puzzles, but actual scenarios a company would face
- Completing challenges earns badges displayed on the portfolio
- Leaderboard potential when scaled to other users

---

## Deployment

**Frontend → GitHub Pages**
```
https://sasi0026.github.io/atlas/
```
- Push changes to `main` branch → auto-deploys in ~2 minutes
- No build step needed — pure HTML/CSS/JS

**Backend → Render**
```
https://eden-api.onrender.com
```
- Connect GitHub repo → point to `backend/main.py`
- Free tier, auto-deploys on push

**Database → Supabase**
- PostgreSQL, fully managed, free tier
- REST API available — frontend can query directly for read operations
- Backend uses Supabase Python client for writes and complex queries

---

## Build Phases

| Phase | What | Status |
|-------|------|--------|
| Phase 1 | Task Manager — projects, skills, goals, blog log | 🔨 In Progress |
| Phase 2 | Public portfolio pages — projects wall, skills badges, blog | ⏳ Planned |
| Phase 3 | EDEN AI integration — Groq + FastAPI backend | ⏳ Planned |
| Phase 4 | Supabase DB — replace localStorage, cross-device sync | ⏳ Planned |
| Phase 5 | Gamification — skill levels, real-world challenges, badges | ⏳ Planned |

---

## Why ATLAS?

Most portfolios are static. They tell you what someone built.

ATLAS shows **how** someone builds — daily, consistently, honestly. Every missed day is visible. Every streak is earned. Every project has a timestamped journey behind it.

When I hand someone this link, they don't see a curated highlight reel. They see the work.

---

## Author

**Sasi** — `github.com/Sasi0026`

*ATLAS carries the world. EDEN navigates it.*
