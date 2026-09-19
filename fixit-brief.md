# FixIt — Project Brief

**Krackeddevs Build Day · Mini Hackathon**
**Built by:** Nuriel Batriesya Binti Mohd Fadzillah
**Build window:** 12:30 – 16:30

---

## The Problem

Every semester, students hit the same handful of lab bugs, environment setup errors, and terminal command issues — a broken `pip install`, a segfault from an out-of-bounds vector access, a `git push` rejected because a teammate pushed first. The fix is usually already known by *someone* in the cohort, but it's scattered across group chats, forgotten Discord messages, or lost entirely once that conversation ends. Students end up re-solving the same problem their seniors (or even their classmates last week) already solved.

**FixIt** is a crowd-sourced repository where students post the bug, the fix, and get it verified by peers who confirm it actually worked — so the next student with the same error finds a tested answer in seconds instead of re-debugging from scratch.

---

## Core Features (Requirement 01 — Main Action)

| Feature | What it does |
|---|---|
| **Search bar + tag filters** | Search by error message or keyword; filter by tag (Linux, C++, SQL, Networking, Git, Python, Terminal — tags are generated dynamically from submissions) |
| **One-click Copy Code/Command** | Every fix sits in a code block with a dedicated copy button, so students can paste the exact command straight into their terminal |
| **Verified fix badge** | When 3+ different students click "This worked for me," the entry automatically flips to a green ✓ Verified badge, so trustworthy fixes stand out from unconfirmed ones |
| **Submit a fix** | Any student can add a new bug + fix with a title, tags, problem description, and the fix itself |

---

## Key Decisions

- **Client-side storage over a backend.** Given the 4-hour window, I built this as a single self-contained HTML/JS file using the browser's local storage instead of setting up a server and database. This let me spend the build time on the actual feature logic (search, filtering, verification threshold) rather than infrastructure, and guarantees it works reliably for a live demo with zero setup.
- **Verification threshold of 3 confirmations.** Chose 3 as a low-but-meaningful bar — enough to filter out one-off flukes, low enough that good fixes don't sit "unconfirmed" forever in a small cohort.
- **Pre-seeded with 6 realistic entries.** So the app doesn't look empty on first load — seeded bugs span all requested areas (Linux, C++, SQL, Networking, Python, Git) to show breadth immediately.
- **Sort by votes, not recency.** The most-confirmed fix surfaces first, since a fix with more peer confirmations is more likely to be correct.

---

## What's Next (if this became a real product)

- **Shared backend/database** so submissions and votes are visible across *all* students, not just the browser they were entered in — this is the main gap between the demo and a real multi-user tool.
- **Duplicate detection** — flag when a new submission looks similar to an existing entry, to keep the repository clean.
- **Comments/discussion thread** per fix, for edge cases ("this also worked on Fedora, not just Ubuntu").
- **Moderation/reporting** for incorrect or unsafe fixes (especially important for terminal commands with `sudo`).
- **Login-based reputation** so verified contributors build trust over time.

---

## Proof to Show

- Live link: search "python", filter by "Linux" tag, copy a fix, and click "This worked for me" 3 times on any entry to watch it flip to Verified.
