# SPEC.md (v1)

## Aim
For [you], a place to put everything down and see only today.
It worked if capture takes under 3 seconds, Today settles in under a minute
each morning, and by week two neither of you keeps a list elsewhere.

## Scope
Android phone, portrait first. Two people, two separate installs, no sharing.
English. Follows the system light or dark setting.
The app asks for no internet permission.

## What it holds
Task: title (required), note (plain text, links open), when (a date, Someday,
or nothing), deadline (optional date), reminder (optional time on its when
date), project (optional), open or done.
Project: a name and its tasks. One level. No areas, headings or tags.

## Lists are views, not places
- Inbox: open, no when, no project
- Today: open, when is today; also any open task whose deadline is today or past.
  Tasks marked evening sit in the same list beneath a thin rule headed
  "Evening". The section appears only when it has tasks. It is not a separate list.
- Upcoming: open, when is a later date, grouped by date
- Someday: open, when is Someday
- Project: its open tasks, its done tasks folded beneath
- Ledger: every done task, newest first, grouped by day
Giving a task a when or a project is what takes it out of the Inbox.

## Behaviors
Capture. Entry points: launcher shortcut, quick-settings tile, share sheet, one
button on Today, and one home-screen widget. The widget is a single bar reading
"Capture" that opens the field. It shows no tasks, so it is never out of date.
A single-line field opens with the keyboard up, typeable within 1 second of the
tap on the owner's own phone, from any entry point. A single-line field opens with the keyboard up,
typeable within 1 second of the tap on the owner's own phone. Return saves and
leaves the field open and empty. Back closes it. A shared item saves and returns
to the app it came from: subject or first line becomes the title, the rest the
note. Capture lands in the Inbox, or in the project if started inside one.
An empty line saves nothing and says nothing. Unsaved text survives an
interruption and is waiting at the next capture.

Morning. On the first open after the day turns, if open tasks are dated before
today, one page asks once: "Left from yesterday" (or "Left from before").
Each row has three answers: Keep (stays in Today), Upcoming (date picker),
Let go (to Someday). One button, Keep all, answers every row. Leaving the page
unanswered is the same as Keep all. After this, no open task has a past when.
There is no overdue pile. The evening mark clears when the day turns.

Placing. Inbox rows carry three quiet actions: Today, a date, Someday.
Tapping a row opens it for the rest: when (Today, This evening, a date,
Someday), note, deadline, reminder, project.

Completing. A tap draws one line through the title and gives one soft haptic.
The row rests about a second, then leaves for the Ledger. Tapping it during
that second undoes it. No snackbar. A done task can be reopened from the Ledger.

Deadlines. A deadline is the only thing that may ask for attention on a list.
Past its date, the deadline text takes the accent. Nothing else does.

Reminders. Only ones the owner sets. They fire at the set minute, survive a
restart and a time zone change, and opening one opens the task. Permission is
asked once, at the first reminder, in one plain sentence. If refused, the time
is not saved, the task says reminders are off in system settings, and the app
does not ask again.

Find. One field in the index. Matches title and note in every list, Ledger included.

Delete. In the open task, in place, one confirmation in plain words. Irreversible.

Export and import. The only settings. Export writes one dated JSON file a person
can read, named [app]-2026-10-06.json, including the Begun date. Import restores
from it.

Begun. Once the Ledger has an entry, under the oldest one: "Begun" and the date
the app was first opened.

## Empty states
- Today, nothing left: the date, and "Nothing left for today."
- Inbox: "Inbox is empty."
- Ledger: "Nothing finished yet."
- Upcoming, Someday: the title only.
No illustration, no encouragement.

## Failure behavior
- Writes: a change is on disk before the screen shows it. Killing the app at any
  moment loses nothing the owner saw saved.
- Unreadable store: a plain page says so in one sentence and offers the daily
  safety copy, then the latest export. The app never starts empty without saying
  so. One safety copy, refreshed daily, held on the device.
- Time: dates are calendar dates, times follow the device, the day turns at 04:00.
- Long text: titles wrap to two lines, then an ellipsis. Full text is in the task.
- Type size: at 200% system font scale, rows grow and nothing clips.
- Motion: with system animations off, every transition is instant.
- TalkBack: every control is labelled. Every row reads title, when, deadline.

## Not in v1
Accounts, sync, sharing, handing over a task or project, recurring tasks,
checklists inside a task, tags, areas, headings, Anytime, calendar view, a Today
widget, natural-language dates, attachments, AI, analytics, crash reporting, ads,
themes.
Reopen sharing only if, during fitting, you catch yourselves texting each other
tasks by hand.
Known gap: recurring tasks. If either of you reaches for them in week one, they
are the first addition.

## One day
Tuesday 07:40. Six tasks are open from Monday. The page "Left from yesterday"
opens. Let go on one, Upcoming on another (Friday), Keep all for the other four.
Today shows four. Three tasks captured last night sit in the Inbox: Today on two,
Someday on one. Under a minute. At 10:15, in a shop: shortcut, "Buy batteries",
Return, Back. It is in the Inbox. At 17:00 the owner taps a task, the line is
drawn, and it leaves for the Ledger.

## Acceptance
1. Capture: tap to saved under 3 s for a 40-character title, from the shortcut
   and from the widget. Ten tries each, median, on the owner's phone.
2. Morning: five carried over, five in the Inbox, all placed in under 60 s, timed.
3. Durability: 100 captures with the process killed at random. None lost, none doubled.
4. Export, wipe, import: identical lists, Ledger and Begun date included.
5. Silence: no internet permission, and no notification the owner did not set.
6. Week two: both still use it unprompted. At day 14, neither keeps a list
   elsewhere. Observed, not built.
