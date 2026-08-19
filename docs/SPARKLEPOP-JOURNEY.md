# ✨ SparklePop — Build-in-Public Journey Log

A running, **evidence-only** record of meaningful SparklePop moments, for turning the real journey into honest content later.

**Rules for this file**
- Capture only events verifiable from the repository or the working session.
- Do **not** invent dates, results, or history. Anything uncertain is marked `⚠️ UNVERIFIED`.
- Dates are **git commit dates** unless noted. A commit date is when work landed, not necessarily when the idea happened.
- Nothing here is published. No social posts are drafted here.

**Content-potential legend:** `LinkedIn` (builder/process/ethics) · `Instagram` (visual/emotional) · `Both` · `Capture only` (log now, not obviously shareable yet).

---

## Featured thread — The Sparkle Egg / hatchling (Aug 2026)

### 1. Game-design review of the Sparkle Egg experience
- **What:** A structured game-design critique of SparklePop for ages 4–8, focused on the Sparkle Egg, delight, agency, retention, and parent trust.
- **Evidence:** Conducted in the working session of **2026-08-18**; outputs preserved in the memory notes and the roadmap that came out of it. The review read the live code in `play.html`, `pet.html`, `index.html`, `play-hub.html`.
- **⚠️ Note:** The review itself is a session artifact, not a committed repo file. The *outcome* (the prototype commit below) is committed and verifiable.
- **Content potential:** `LinkedIn` — "I ran an AI game-design review over my kid's app and it changed what we built next."

### 2. Discovery: hatchlings disappeared after 0.8 seconds
- **What:** The Sparkle Egg's biggest emotional beat — a creature hatching — was being deleted 800ms after it appeared. The child couldn't touch, keep, or react to it.
- **Evidence (strong, code-level):** The pre-change `hatchCreature()` in `play.html` contained `setTimeout(() => hatched.remove(), 800)`, and the `hatchPop` animation ended at `opacity:0`. Both are visible in the diff of commit **`9a539c7`** (2026-08-18).
- **Content potential:** `Both` — strong, honest hook. Instagram can show the vanish vs. stay side by side; LinkedIn carries the "we optimized the magic away by accident" insight.

### 3. Decision: test a session-only hatchling that stays and responds
- **What:** A deliberately tiny experiment — when a creature hatches it now **stays for the session** and reacts to a tap (happy hop + existing glitter, soft sound, floating heart). No persistence, naming, scores, or new systems. One hypothesis only: *does staying + responding build more attachment/delight than disappearing?*
- **Evidence:** Committed and pushed to production (`main`, GitHub Pages → sparklespop.com) as **`9a539c7`** on **2026-08-18**, "Prototype: hatched creatures stay for the session and respond to taps."
- **⚠️ Result status:** **PENDING.** Not yet tested with a child. No outcome exists yet — do not frame as a success.
- **Content potential:** `Both` — the "tiny bet, about to be judged by a real kid" tension is the story.

### 4. Reached the hypothesis via a custom "Kids Game Designer" AI skill
- **What:** The review and hypothesis were produced by a purpose-built SparklePop Kids Game Designer skill acting as a critical children's game designer — not generic prompting.
- **Evidence:** The skill file exists at `~/.claude/skills/sparklepop-kids-game-designer/SKILL.md` (created 2026-08-18, this session).
- **Content potential:** `LinkedIn` — the meta-story of building an AI *teammate* with a point of view, not just a chatbot.

---

## Session thread — Rebuilding how play begins (2026-08-19)

A single working session, driven by the SparklePop Kids Game Designer review loop. All items below are **shipped to production** (`main` → GitHub Pages → sparklespop.com) and verifiable in git. **Result status for every item: PENDING a real child's verdict** — none is tested with Anya yet; do not frame as "working" or "loved."

### 1. The "arrival" moment — a calmer way in
- **What:** Play mode was opening fast and busy (score bar, progress, worlds, spawns all at once). It now opens on a calm sleeping unicorn ("tap to wake the magic ✨") with the chrome hidden; the child's first tap wakes it and the world blooms open. Session-only, no persistence/scores.
- **Evidence:** `59f676d` (2026-08-19). Also verified in-browser this session.
- **Content potential:** `Instagram` (visual before/after) · `Both`.

### 2. Progressive lands — a decision reversed
- **What:** Only Magic Garden is open at start; Candy Land (12✨), Under the Sea (30✨) and Outer Space (55✨) now reveal one at a time as sparkles are collected, each with a symbol-bloom reveal.
- **Honest tension:** This **reverses** an earlier bet — `dd68474` (2026-08-16), "Open all worlds from the start so travel actually changes the scene." The unlock machinery already existed; one line was forcing all worlds open.
- **Evidence:** `405ef48` (2026-08-19).
- **Content potential:** `Both` — "I changed my mind" + community poll.

### 3. Removed the "My Pet" button from play mode
- **What:** Removed the My Pet link from play mode's bottom bar and title screen (My Pet still lives on the hub) to keep the world uncluttered.
- **Evidence:** `59f676d`, `405ef48` (2026-08-19).
- **Content potential:** `Capture only` (part of the declutter thread, not a standalone story).

### 4. Parent-facing "peek at the play" on the landing page
- **What:** A warm, parent-facing card on `index.html` explaining what a child plays (pop & collect, catch unicorns, worlds that open up, "play, never pressure"). Kept parent-facing on purpose — the ethos is "never make a child read instructions."
- **Evidence:** `9ddb216` (2026-08-19).
- **Content potential:** `LinkedIn` (design-ethics: instructions for parents, not kids).

### 5. Flying-sparkle score feedback
- **What:** Earned sparkles now visibly fly in an arc up into the ✨ stash (1 per bubble pop, a burst of 5 per unicorn catch), so collecting is visible from the first tap. Pure juice; counts/mechanics unchanged.
- **Evidence:** `9ddb216` (2026-08-19).
- **Content potential:** `Instagram`.

### 6. Growing unicorn herd
- **What:** Caught creatures no longer vanish — each trots into a herd meadow strip along the bottom and stays (across worlds too), turning the 🦄 count into something a child can see. Capped at 16.
- **Evidence:** `73e037f` (2026-08-19).
- **Content potential:** `Instagram` · `Both`.

### 7. Wordless "quest to the next surprise" progress track
- **What:** Replaced the unreadable "Next: 🎀 Bow (8✨)" label with a wordless quest track: ✨ → a filling bar → a mystery gift 🎁 that stays dim/grey when far, colours in and grows as you approach, wiggles when close, then bursts to reveal the reward before resetting. Driven by the "make progression legible to a pre-reader" thread of the game-design review.
- **Evidence:** `73e037f` (2026-08-19).
- **Content potential:** `Both` — "our progress bar had words a 4-year-old can't read."

### Meta
- **What:** Items 5–7 came out of a scoring/feedback critique run through the SparklePop Kids Game Designer skill during this session, which explicitly pushed *against* a numeric score/level ladder (off-ethos) in favour of visible, non-competitive growth.
- **⚠️ Note:** The review itself is a session artifact; the commits are the verifiable outcome.

---

## Earlier milestones (verifiable from git history)

| Date | Milestone | Evidence (commit) | Content potential |
|---|---|---|---|
| 2026-06-25 | Repo begins — first files uploaded | `e8c57d9` | Capture only |
| 2026-06-26 | Deploy-ready; `CNAME` for sparklespop.com; GitHub Pages; Pet module + explorable worlds + home hub added | `b5cef3f`, `d483608`, `7ed2ee9`, `2b79530` | LinkedIn |
| 2026-06-27 | Origin at a **hackathon** (per `journey.html`); feature packs — egg surprises, baby companion, dancing unicorn, "show mummy", non-blocking milestones, food removed | `7b970fb`, `c3ded50`, `a1bcd30` | Both |
| 2026-06-28 | Microsoft Clarity analytics added to game + hub | `77b8800`, `19df616` | Capture only ⚠️ (see Future Story #2) |
| 2026-07-19 | Story landing page + `journey.html` timeline; reframed every feature as "Anya wants X"; **Anya's own bug reports** logged and fixed; learn-a-fact eggs; 15-min play check-in | `1aa79ab`, `b8aef9c`, `3f86295`, `527220d`, `362359f` | Both |
| 2026-07-19 | Fun fact made gentle: once/15min, non-blocking, toddler wording, softer voice | `711f0cb` | LinkedIn |
| 2026-07-20 | Standalone Paint page; landing-page learning egg (40 facts) | `483d288`, `ec463a0`, `3500...` | Instagram |
| 2026-08-16 | 15-minute play limit + end-of-session **learning recap** ("show Mummy what you learnt"); toddler-friendly Paint; removed the magic counter; worlds open from the start | `3500d1a`, `71fd4af`, `dd68474` | Both |
| 2026-08-18 | Hatchling prototype shipped (thread above) | `9a539c7` | Both |
| 2026-08-19 | Rebuilding how play begins — arrival moment, progressive lands (reverses `dd68474`), parent-facing "peek at the play", flying-sparkle feedback, growing herd, wordless quest track (session thread above) | `59f676d`, `405ef48`, `9ddb216`, `73e037f` | Both |

**⚠️ UNVERIFIED details:** the specific hackathon (name, exact date) is only *claimed* in `journey.html` ("Anya's mom wanted to make something for Anya at a hackathon") — not independently verified here. Treat as the family's own account, not a checked fact.

---

## The 3 strongest future stories worth documenting

1. **Anya's verdict on the hatchling.** The loop closes when a real 6-year-old tests whether the creature-that-stays matters. "Our game deleted the magic after 0.8 seconds. Our AI game designer caught it. My daughter decided if it was right." — highest-tension, most authentic story. Capture her actual reactions (the 5 observation signals), win or lose. `Both`.

2. **The parent-trust / privacy decision.** SparklePop runs Microsoft Clarity (session recording) on pages a young child uses. Choosing to review and likely remove it — putting trust above analytics on a kids' app — is a rare, credible builder-ethics story. `LinkedIn` (strong), leaning `Both`. *(Do the privacy review first; don't tell the story before the decision is real.)*

3. **Building an AI *teammate*, not just using AI.** The repeatable loop — AI reviews → hypothesis → tiny build → child tests → learn → tell the story — and the mum-and-daughter co-creation it wraps (Anya's real feature requests and bug reports already in the git log). This is the durable, differentiated narrative. `Both`.

---

*Log maintained as evidence-first. Publishing and post-drafting are separate, later steps.*
