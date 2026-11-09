# Study Planner

A calm, single-page weekly planner that builds your study schedule **around your real life**, not just your classes.

Open `index.html` in any modern browser. There's nothing to install, no account to create, and no internet needed.

---

## Why this was made

Most study planners assume your week is empty apart from class. Real student weeks aren't like that: there's band rehearsal, a part-time job, the gym, club meetings, hobbies. Some of those can never move, some can shift a little, and some could be dropped if an exam is coming.

This planner was made to:

- **Plan study time automatically**, giving more of it to courses that are harder, that you feel less confident in, and whose deadlines are closer. Deadlines can be exams, projects, papers, presentations, problem sets, quizzes or readings, including ones that repeat every week.
- **Respect how flexible each commitment is**, so it never moves your classes but can slide your gym session to a better time.
- **Be honest when there isn't enough time.** It tells you exactly how short you are and which optional things you could drop to make room.
- **Explain itself.** Every study session can tell you *why* it was placed where it is.
- **Work for any student.** No personal data is built in, everything stays on your own device, and it runs from one file.

---

## The core idea: flexibility levels

Every commitment gets one of four levels:

| Level | What it means | Example |
|---|---|---|
| 🔒 **Locked** | Never moves and never gets skipped | Lectures, marching band rehearsal |
| ↔ **Movable** | Can slide anywhere inside an earliest–latest window, with a set length | Gym, any 60 minutes between 4 and 9pm |
| ⏭ **Skippable** | Can be dropped (with a warning) if the week is overloaded | A club meeting, one rehearsal before a big exam |
| ◌ **Optional** | Only appears if there's free time left over | Guitar practice, hobbies |

Each level has its own look on the calendar, so you can tell them apart at a glance.

---

## Features

### Setup
- **Courses:** name, color, difficulty (1–5), your current confidence (1–5), and any number of **deadlines** (see below).
- **Commitments:** weekly repeating events with days, times, flexibility level and an optional location. Movable ones get a time window and a length instead of fixed times.
- **Settings:** wake and sleep times, study session length, break length, maximum study hours per day, and preferred study times (morning, afternoon, evening, night).

### Deadlines: not just exams
Not every course has an exam. Each course can have any mix of:

| Type | Typical prep* | Prep starts |
|---|---|---|
| Exam | 1h + 0.5h × difficulty × (6 − confidence) | from today |
| Project | 8h | from today |
| Paper / essay | 6h | from today |
| Presentation | 4h | 14 days before |
| Problem set | 3h | 7 days before |
| Quiz | 1h | 5 days before |
| Reading | 1.5h | 4 days before |
| Other | 2h | 7 days before |

\*Non-exam amounts are for a course at difficulty 3 and confidence 3. They're scaled up for harder or less-confident courses and down for easier ones.

For each deadline you can:
- give it a **title**, for example "Lab report" or "Chapter 5 reading".
- type your own **prep hours** if you know how long it takes. Leave it blank to use the estimate, which the editor shows live.
- tick **Weekly** for things due every week, like a reading quiz every Tuesday. You can add an **until** date for the last one. Each week's prep only starts after the previous week's is due.

### ⚡ Quick add: type or paste your class schedule
Available from both the **Courses** and **Commitments** tabs. Instead of entering each class by hand, type one class per line in this order, separated by commas:

**Class name, Days, Time, Location (optional)**

```
Calculus II, MWF, 9:00-10:15am, Thornton Hall 101
BIO 2010, TuTh, 1130am-1245pm, Gilmer 130
Organic Chem Lab, Wed, 1-4pm
```

- It understands common ways of writing days, in upper or lower case: `MWF`/`mwf`, `TTh`/`tth`, `TR`/`tr`, `TuTh`, `Mon/Wed`, `M-F`, `Thursday`.
- It understands times with or without a colon: `9-10:15am`, `2pm-3:15pm`, `1130am-1245pm`, `1130 am`, `930-1045`, `14:00–15:15`, `3:30pm to 4:45pm`.
- Text pasted from a school portal usually works even when it isn't in that order. Course codes like `CS 2100-001` aren't mistaken for times.
- It also reads tab-separated text copied from school portals or spreadsheets.
- You see an **editable preview** first, and anything it had to guess (like am/pm) is shown.
- It can **create the matching courses** at the same time, with an optional first deadline of any type. A lecture and lab of the same course become one course.
- Pasting the same schedule twice won't create duplicates.

### Automatic scheduler
Each week is rebuilt every time something changes, in this order:

1. **Locked and Skippable** items go in at their fixed times.
2. **Movable** items go into the best spot inside their window. The best spot is the one that leaves your free time in usable blocks. The item with the tightest window is placed first.
3. **Study sessions** fill the free time, planned **per deadline**:
   - Each deadline needs a certain amount of prep (see the table above). Completed sessions for it count against that.
   - That prep is spread evenly over its prep window, which gives **this week's target** for it.
   - Deadlines that are due sooner, in harder courses where you feel less confident, get first pick of the slots.
   - Sessions prefer your preferred times, are spread across days, include breaks, never exceed your daily maximum, and always land before the deadline they're for.
4. **Optional** items appear only where time is still free.

### Conflict handling
If a deadline can't get enough prep time, a banner explains:

- **what's short and why**, for example "Organic Chemistry needs 11h for **Midterm (exam)**, due Fri Nov 13; only 8h fits. 3h short. It's due soon, so only 4 study days are left, and they are full."
- **specific suggestions**, for example "Skipping **Thursday's Club meeting** frees **1h 40m** for **Organic Chemistry** (Midterm)." The planner tests each possible skip, so the hours shown are the real study time gained.

You can **Skip it** or **Keep** each suggestion, and the schedule updates instantly. Skipped items stay on the calendar as faint outlines you can click to restore. Skips only apply to the week you're viewing.

### Interacting with the calendar
- **Click** any block to view or edit it. Clicking a study block opens its course plus a "This session" panel.
- **Drag Movable items** up or down. Their allowed window lights up, and they can't leave it.
- **Drag study blocks** to any free time. Days you can't use are shaded, and drops onto a class or other fixed item are refused with a reason.
- **✓ Check off** completed sessions with the circle on each study block.
- **Explain-why tooltips:** hover over (or Tab to) a study block to see every reason it's there. For example: which deadline it's prep for and how soon it's due, how much prep that needs, its priority rank, whether it's a preferred time, and how it spreads your week.
- Sessions you move or check off are **pinned** for that week, so the planner keeps them in place and plans around them.

### Progress sidebar
- A **This week** card shows hours studied vs. planned and the next thing due.
- Each course shows a **countdown to its next deadline** (with its name), a **progress bar** (studied vs. planned vs. target) and whether it's short on time.
- **Detailed view** adds what's coming up next, totals, priority rank, and the difficulty and confidence levels.

### Views and navigation
- **Simple / Detailed toggle.** Simple is calm, showing names only. Detailed adds times, locations, reasons, and Optional items that didn't fit.
- **Week navigation** (‹ Today ›), with every due date marked on the calendar header, for example "Exam · Chemistry" or "Quiz · Psychology".
- **Responsive:** on phones the calendar comes first, scrolled to today.

### Data
- **Saves automatically** in your browser (localStorage).
- **Data menu:** Load sample data, Export JSON (backup), Import JSON (restore, checked before anything is replaced), and Clear all.

---

## Keyboard shortcuts

| Key | Action |
|---|---|
| `[` / `]` | Previous / next week |
| `T` | Jump to this week |
| `D` | Toggle Simple / Detailed view |
| `Alt` + `↑` / `↓` | Move the focused block 15 minutes |
| `Alt` + `←` / `→` | Move the focused study block one day |
| `Esc` | Close a dialog, menu or tooltip, or cancel a drag |
| `Tab` | Move between everything; a "Skip to calendar" link appears first |

---

## Getting started

1. Double-click `index.html`.
2. Try **Data → Load sample data** to explore, or start fresh:
   - **Commitments → ⚡ Quick add** to paste your class schedule
   - **Courses** to set difficulty and confidence, and add deadlines: exams, projects, papers, weekly quizzes or readings
   - **Settings** to set your wake and sleep times and study preferences
3. Add other commitments (work, practice, gym) with the right flexibility level.
4. During the week, tick off sessions as you finish them.

---

## Where your data is saved

| What | Where | Notes |
|---|---|---|
| The planner (`index.html`) | This folder | Permanent; it's just a file |
| Your data | Inside the browser you open it with | Kept between visits in the **same browser on the same computer** |

Your data **will not** follow you to a different browser or computer, and clearing your browser's site data or using a private window will remove it.

**Back up regularly:** use **Data → Export JSON** and save the file in this folder. Use **Data → Import JSON…** to restore it anywhere.

Nothing is ever sent to a server. Your schedule stays private on your device.

---

## Sharing it as a website

Because it's a single static file, it can be hosted for free so others can use it from a link:

- **GitHub Pages:**
  1. Create a public repository and upload `index.html`.
  2. Go to **Settings → Pages**, choose **Deploy from a branch**, then `main` / root.
  3. Your site will be at `https://<username>.github.io/<repo-name>/`.
- **Netlify Drop:** drag this folder onto app.netlify.com/drop.

Each visitor gets their own private planner, with data in their own browser. There are no accounts and no syncing between devices.

---

## Known limitations

- **Check off sessions on the day you do them.** The planner only auto-places study from today onward, so unticked sessions from earlier days disappear. Ticked or moved ones stay.
- **New courses from Quick add** start at difficulty 3/5 and confidence 3/5. If you didn't give a first deadline, the course has none, and no study is planned for it until you add one in Courses.
- **Prep estimates are rough starting points.** If you know a project takes 15 hours, type that into its prep hours.
- **Weekly deadlines repeat on the same weekday** as their first due date. For an irregular schedule, add each due date separately.
- **Quick add reads typed or pasted text only**, not screenshots or PDFs.
- **Overnight events aren't supported**, for example 10pm–1am.
- **Ticking or moving one session** can shift a few others slightly, because the week is re-planned around it.

---

## Technical notes

- **One file:** `index.html` holds all the HTML, CSS and JavaScript.
- **No frameworks, libraries or external requests.**
- **Works in current Chrome, Edge, Firefox and Safari**, with light and dark mode following your system setting.
- **Accessible:** keyboard-operable throughout, labelled controls, and reduced motion respected when your system asks for it.
- **The `.claude` folder** is only from the development and testing setup and isn't needed to run the planner.
