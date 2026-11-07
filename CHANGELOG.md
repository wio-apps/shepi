# Release notes

Every version of Shepi for Herdr, newest first. The same notes are at [shepi.app/releases](https://shepi.app/releases).

## Shepi 1.4.1

Agents reach Shepi reliably, and every answer and setting stays where it belongs.

- **Agents reach Shepi whenever it's open.** They no longer say Shepi isn't open while it is.
- **Codex and Grok Build keep your settings.** Shepi no longer removes settings you chose in Codex or Grok Build.
- **Every answer reaches its own question.** Your answer always goes to the question you answered, and an agent that asks the same question again right away gets a new card.
- **Permissions as they are now.** When an agent asks whether Shepi has a permission, it hears what is turned on now, even if you just changed it in System Settings.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.4.0

Your agents use Shepi on their own, every question waits in one card, and Shepi speaks Japanese and Chinese.

- **Your agents use Shepi on their own.** Claude Code, Codex and the other agents find Shepi among their tools, with nothing to set up. Ask for a page "on your right" or tests "next to you", and the agent does it.
- **Agents hand work on to fresh agents.** When an agent finishes, a fresh one can start with the next task, right away or at a time you choose, even with Shepi closed.
- **See what an agent is working on.** Its current step and how far along it is show under its name, and a click shows the whole task list.
- **Answer your agents from anywhere.** Every question from every agent waits in one card at the top right, without getting in your way. Answer with a key, in your own words, or with a screenshot or files. A question waits through a restart of Shepi, and your answer still reaches the agent.
- **See what an agent wants to run.** When an agent stops to ask permission, its row shows what it wants to do.
- **Notifications say which agent** and what happened. Click one to go to its pane.
- **The Agents list stays put.** Rows no longer jump around as agents change state, and you can sort and pin them.
- **Changes in a card over your panes.** It stays open as you move between panes, and undoing a change can itself be undone.
- **Settings, reorganized,** so each setting is where you'd look for it, and search finds any of them.
- **Shepi in Japanese and Chinese,** following your Mac's language or the one you pick. shepi.app has both too.
- **Easier to read, calmer to look at.** Larger text in the Mac's own font, a faint line between the sidebar's rows, and no scroll bars.
- **Macros.** Your agent can write them for you, and a macro can now press ctrl, alt and shift with any key.
- **Send a pane to the background.** It keeps running, and the tray beside Find brings it back.
- **Shepi reopens where you were,** on the same machine, space, tab and pane.
- **Panes on any side.** Agents can open panes above, below, left or right of themselves, and you can split a pane from its header and resize the sidebar.
- **Closing a tab shows the next one.**
- **Worktrees and Git in one place.** The worktree list ticks the safe ones for you, and the status line's Git part shows what changed and what's left to push.
- **Every machine in its own colour,** so you always know where an agent runs.
- **Lighter on your Mac,** especially while agents are busy.
- **Fixes.** Scrolling stays smooth while a program prints. Copying in a pane on another machine reaches this Mac's clipboard. A question no longer shows twice or comes back after it was withdrawn. Esc leaves copy mode at once, and Shepi opens normally when the Mac is offline. Terminals in view keep drawing when macOS wrongly thinks Shepi's window is covered.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.4.0-acceptance

# Shepi 1.4.0: the owner's acceptance tests

The release waits until every line below passes on the owner's Mac, with the build `make install` puts in
`/Applications` (the release configuration). These are the checks only a person at the screen can make: real agents
deciding on their own, real notifications, a real second machine, how it feels. Everything else is proven by the
items' own tests before the build reaches you.

**Setup:** this Mac plus one server machine (workbox) connected in Shepi; a fresh Claude Code and a fresh Codex, each in
its own Shepi pane, not told anything about Shepi. Mark a line `[x]` when it passes; when one fails, write what you saw
under it. A failure goes back to the implementer as a bug before the release.

## 1. Updating

- [ ] **1.1 The update.** From 1.3, take the update Shepi offers. 1.4.0 opens with your licence, machines, spaces and
  macros as they were (each macro with its short id in the editor).
- [x] **1.2 Agents set up.** On this Mac and on workbox, each installed agent lists Shepi among its tools (Claude Code:
  `/mcp`; Codex: `/mcp`), the old `shepi…` skill folders are gone, Herdr's skill is there once, and any skill or
  instruction of your own is as it was. Pi starts without a collision warning. Settings › Agents › Set up again says
  "Done on 2 machines".
  Passed 2026-11-06 (owner): in john's account, on the build with the 3.2b fixes, Set up again said "Done on 2
  machines". In alex, checked from the shell: Claude Code and Codex list `shepi`, no old `shepi…` folders, Herdr's
  skill once per agent. The morning's "Couldn't set up everything" ran on a build that didn't record why.
- [x] **1.3 macOS.** On macOS 15 or later only (the download page and the app say so).
  Passed 2026-11-06, checked from the shell: the installed app requires macOS 15.0; the site's pages say "macOS 15 or
  later" in the source; the live site takes them with the release's deploy.

## 2. Agents use Shepi without being told (Claude Code and Codex, each)

Say these in your own words, one at a time. Pass: the agent does it through Shepi first, with no browser panel,
browser tool or computer use, and without you mentioning Shepi.

- [x] **2.1** "open google on your right": the page opens in a pane right beside the agent.
  Passed 2026-11-06 (owner), Claude Code and Codex, after a fix: with Shepi's window off screen (another account on the
  screen) every pane an agent asked for was refused.
- [x] **2.2** "run the tests next to you": a terminal pane beside it runs them.
- [x] **2.2b** "open google above you", then "run the tests on your left": each opens on that side, the agent's own pane unchanged.
- [x] **2.3** "I need to pick between two names, ask me": a question card with its two names, each with a line on what it means.
- [x] **2.4** "make me a key that switches you to the fast model": a macro is saved; pressing its key does it.
- [x] **2.5** "plan this and keep me posted" (on any real task): "2 of 5 · …" appears under its name and moves on as it works.
- [x] **2.6** "when you're done, start a fresh agent for the next item": when it stops, a new agent starts in its pane with that prompt.
  2026-11-06 (owner): **Codex passed; Claude Code failed.** Asked to "start a fresh agent for the next item", Claude Code
  ran its own built-in sub-agent instead of `shepi_next`, although the tool's description says "not a sub-agent inside
  you" and names that phrase. Fixed the same day (the installed instructions and the tool's words; real Claude Code
  runs: 4 of 4 call `shepi_next` now, 2 of 2 used its sub-agent before). Checked again by the owner, 6:42 PM: a fresh
  Claude Code started in its pane with the next prompt and listed the TODOs. Passed.
- [x] **2.7** "start two fresh agents at <a minute from now>, one to list the TODOs, one to count the tests": at that minute both start.
- [-] **2.8** Give each a four-step job and say nothing about lists or progress: "1 of 4" appears under its name and
  moves on as it works.
  Dropped by the owner, 2026-11-06: "Discard this test; it itself has problems." (2.5 covers the step line.)

## 3. Questions

- [-] **3.1 One queue.** Make the Claude Code here and the Codex on workbox both ask. One card at the window's top right,
  oldest first, "1 of 2"; the asker's mark and name on it; its pane glows; the next question follows when you answer.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [x] **3.2 From anywhere.** From a third pane, ⌃B a gives the card the keyboard (only then do the digits show); a number
  key answers; Go to pane takes you to the agent that asked (it lights under the pointer); Esc returns to your pane.
  Passed 2026-11-06 on a test Shepi (`fidelity/questions/section3.sh`, the agent played through Shepi's own tools):
  from a third pane ⌃B a gave the card the keys, G went to the asking pane with the card keeping them, Esc gave them
  back, 2 answered "Wait".
- [x] **3.2b Never in the way.** With a card up and holding the keyboard, ⌘T opens a tab and you type there; paste a
  screenshot into the answer: the agent reads it. The card's context shows lists, code and a table formatted, and a
  drag across them copies plain text.
  Passed 2026-11-06 (owner), after two fixes: part of a numbered line copied with its number, and a screenshot
  pasted before picking an option was dropped. Both rechecked on the new build.
- [x] **3.3 Your own words.** "Write your own answer" sends your sentence; the agent carries on with it.
  Passed 2026-11-06 on the test Shepi: "The person wrote: deploy after lunch".
- [x] **3.3b It waits.** Ask a Claude Code here and the Codex on workbox to ask you something, and leave each card for
  6 minutes: each agent stays waiting (no reply in its chat yet); answer, and each goes on with your answer by itself.
  2026-11-06, the Claude Code half on a test Shepi (`long-waits.sh waits`): a real Claude Code with Shepi's own entry
  asked, waited 372 s with no reply, then answered "Deploy" as chosen. The Codex-on-workbox half is open.
  The Codex-on-workbox half dropped by the owner, 2026-11-06; passed on its Claude Code half.
- [x] **3.4 In the terminal instead.** Answer a question in the agent's own pane: the card goes by itself.
  Passed 2026-11-06 on the test Shepi: "yes" and Return in the agent's pane; the call read "The person answered in
  your terminal", the card went.
- [x] **3.5 Nobody answers.** Settings › Agents, "If a question isn't answered" at 5 minutes. Leave a question alone: at
  5 minutes it leaves the card, the agent asks in its terminal, and the inbox keeps it. With the Mac untouched for longer
  than that, a new question still comes up on the card.
  Passed 2026-11-06 on a test Shepi (`fidelity/questions/long-waits.sh nobody`): left alone, the question left the card at
  5 min 9 s, the call read "away: …", the inbox kept it, and the next question came up on the card.
- [x] **3.6 Many answers.** Ask an agent to let you pick from fifteen or more items with several allowed; tick them all and
  Send: the agent says it got every one.
  Passed 2026-11-06 on the test Shepi: fifteen items, all ticked, Send; the call got all fifteen.

## 4. Notifications (Shepi in the background, Notify me: When away)

- [-] **4.1 Each kind.** A question, an agent stopped at a prompt, one done, from here and from workbox: Shepi's icon; the
  task as the title; "claude is waiting for your answer" (and so on) under it; "Worked 12 min · workbox" last. Herdr's
  sound with each.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [-] **4.2 One machine.** Disconnect workbox: the last line is "Worked … min" with no machine.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [x] **4.3 The click.** Clicking one lands on that agent's pane (a question: with its card open).

## 5. The window

- [x] **5.1 Split button.** Hovering a pane header shows the split button; it splits at once, with no Web Page item.
- [x] **5.2 Send to background.** The header's first button puts a working pane away; the tray beside Find lists it;
  Bring Back returns it where it was; a pane that needs you while away is announced as usual.
- [x] **5.3 The sidebar's width.** Dragging the panes' left edge resizes the sidebar (no line on the sidebar's own edge;
  double-click resets it); a pane never resizes instead.
- [x] **5.4 Find and ⌘E.** Both open below the pane headers, not over them.
- [x] **5.5 The task card.** Resting on an agent's step line (its third line), or clicking it, opens its card beside
  the sidebar; resting elsewhere on the row opens nothing and a click there switches agent; passing over rows leaves no
  card behind; it stays while you move into it; it shows every task from the top, with both header lines and each finished task's time, and
  nothing lies over a row.
- [x] **5.6 Times.** Each agent row shows how long it has worked in all (not just this turn); its task card's header shows how long the current step has taken.
  5.1–5.6 passed 2026-11-06 (owner, on the build installed 7:22 PM).
- [x] **5.7 Status line.** A message stays long enough to read and act on; clicking the folder opens it in the Finder,
  ⌥-click copies its path; nothing in the line is cut mid-word.
- [-] **5.8 Machines.** With workbox connected, every agent row names its machine: "Local" with this Mac's own kind of
  computer in teal, workbox with a server in its own colour; the same marks and colours in the sidebar's headers, Find
  and the question card.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [x] **5.9 Worktrees.** View › Worktrees (⌥⌘W): one list; the safe ones are ticked; Remove takes exactly the ticked
  ones. Change files in one worktree and Refresh: its size and last activity change. New worktree in a space with panes
  in two repositories offers both, starting on your pane's.
- [x] **5.10 A page's name.** An agent opens google.com beside it: its tab and header say Google.
- [x] **5.11 Zoom.** Zoom a pane while the agent beside it works: it stays drawn the whole time.
- [-] **5.12 Copy mode.** In a workbox pane, enter copy mode, move by words quickly, press Esc: it leaves at once.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [x] **5.13 Changes.** Open Changes (⌃B d): a card over the right of your panes; switch pane, tab and space: it stays
  and doesn't change; z zooms it and back; expand a file an agent keeps changing: its lines appear and stay. Undo
  changes to two files (one new): the sheet says what happens to each, in red; ⌘Z brings them back.
- [x] **5.14 The Agents list.** Two agents whose states keep changing for a minute: their rows never swap; a new agent
  appears at the bottom; Sort By › Name and back to Created.
  5.7, 5.9–5.11, 5.13, 5.14 passed 2026-11-06 (owner).
- [x] **5.15 Settings.** Every section holds what its name says; search "cookies", "update", "herdr" finds them; no
  scroll bar anywhere in Settings with "Show scroll bars: Always"; every text button lights under the pointer.
  2026-11-06: the search part checked (`SettingsSearchTests`): cookies → Clear web panes' data (Privacy), update →
  Check for updates automatically (Shepi), herdr → Herdr's settings. The rest is the owner's eye.
  Passed 2026-11-06 (owner): sections and text buttons. The scroll-bar step dropped: Shepi has no such setting and
  never should (owner: "false test").
- [x] **5.16 Closing a tab.** Three tabs, close the middle one: the one on its right shows.
  Passed 2026-11-06 on a test Shepi (`fidelity/window/close-middle-tab.sh`): two closed, three shows; the last
  closed, the one on its left shows.
- [x] **5.17 Sizes and fonts.** Shepi beside VS Code: the sidebar, tabs, status line and a card read at the same sizes;
  tabs, paths and keys in the Mac's font; a tab's and its header's agent marks the same size as their names.
- [x] **5.18 Changes' edges.** In Changes, drag the edge after the file list and, in Split, the middle: a blue line
  and the resize cursor under the pointer, live resizing, each stops at its limit; a double-click puts it back; quit and
  reopen, the widths are kept. With the old side narrow, "⋯ 6 unchanged lines" reads whole.
  Passed 2026-11-06 (owner), after two fixes: Split's middle grabbed across the whole gap, and the list edge's cursor
  held over the diff; both edges show the left-right arrows and no line (the owner's call).
- [x] **5.19 The Git card.** Rest the pointer on the status line's changes, at its right end: the card opens just above
  them, inside the window, with no "0 …" anywhere; in a clean folder it says "Nothing to commit…", with the other
  worktrees under it if there are any.
- [x] **5.20 The inbox.** Open it: the window's traffic lights stay coloured; Esc closes it and the pane under it gets
  nothing; one click on a row takes you there.
- [x] **5.21 Macros.** Settings › Macros opens with "Your agent can write macros for you"; Copy puts the example on the
  clipboard.

## 6. How it feels

- [x] **6.1 Claude Code's input.** Its input area has the pane's own colour, not a darker strip.
- [x] **6.2 The cursor.** Switching tab and back, clicking into a pane: the cursor shows at once.
- [x] **6.3 Typing.** Fast typing into Claude Code doesn't stutter.
- [x] **6.3b Scrolling.** Scroll a long Claude Code session and a long Codex session, slowly and fast, both ways, while
  each keeps printing: both smooth, no pauses, nothing landing after your fingers lift.
- [x] **6.3c Lighter.** One working Codex for 30 s: Shepi uses clearly less CPU than 1.3.0 did (about 10–16 % of one
  core then); with the screen locked, near 0 %.
  Passed 2026-11-06, measured from here (`ps` once a second on the owner's Shepi, 30 s each, a Codex writing all the
  while): in view, mean 7.4 %, median 5.0 %, peak 41.3 % of one core; screen locked, mean 0.8 %, median 0.7 %, peak 3.3 %.
- [x] **6.4 Sizes.** Open the same session in Herdr's own terminal and in Herdi too: each pane behaves as it does in
  Herdr's terminal; after Herdi goes to the background, Shepi's panes return to Shepi's size by themselves.

## 7. Coming back

- [x] **7.1 Quit and reopen.** Same machine, space, tab and pane.
  Passed 2026-11-06 on test Shepis (`fidelity/window/reopen-where-you-were.sh`): left on tab two, its split pane
  focused, quit; Herdr's focus moved meanwhile; the next Shepi opened on tab two, that pane.
- [-] **7.2 Restart the Mac**: the same, and agents kept running.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [-] **7.3 Turn Wi-Fi off and on.** Dropped by the owner, 2026-11-06 ("I won't turn the wifi off, I'm working").
- [-] **7.3a Open before the network.** With Wi-Fi off, open Shepi (and once at login, with Open at login on): it
  opens unlocked, no sign-in card and no trial-over sheet; turning Wi-Fi on changes nothing.
  Dropped by the owner, 2026-11-06, with 7.3.
- [-] **7.4 Copy on workbox.** Text copied in a workbox pane pastes on this Mac.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).
- [-] **7.5 Machines and commits.** Two machines show as flat headers with their spaces under them; a space whose panes
  are in two repositories shows both repositories' commits to push and pull added together.
  Dropped by the owner, 2026-11-06 (the workbox and Mac-restart checks).

## 8. Languages

- [x] **8.1 Japanese.** Set Shepi to Japanese in Settings › General › Language: it changes at once, no relaunch, your
  terminals keep drawing. The window,
  sidebar, question card, notifications, Find, ⌘E, the tray and every Settings pane read in Japanese; names, commands
  and the terminal stay as they are; nothing is cut that isn't cut in English.
- [x] **8.2 Chinese.** The same in Simplified Chinese; then "Same as your Mac" goes back to the Mac's.
- [x] **8.3 The website.** shepi.app/ja/ and shepi.app/zh/: the home page, Guide (its pictures in that language) and
  Compare read in the language; the footer's switch moves between the three.
  Passed 2026-11-06 on a local build of the site (the live one takes it with the release's deploy): ja and zh home,
  Guide and Compare declare their language, no English left (no run of five English words), the Guide's 10 pictures
  are each language's own, and the footer switch links the same page in all three.

## Shepi 1.3.0

A brighter sidebar that tells you more at a glance, a roomier worktree list, and typing that takes a pane back.

- **Push and pull at a glance.** Each space shows how many commits are waiting to be pushed and pulled.
- **Space tiles you can tell apart.** Each space has a tile in its own colour with a letter or an emoji.
- **Agents lead with their own mark.** Each agent row starts with its maker's mark, and its state sits on the right.
- **A tidier sidebar.** Spaces and agents line up, with one badge for each state.
- **⌘B shows and hides the sidebar.**
- **A roomier worktree list.** It opens in the middle of the window, and Shepi remembers the size you give it.
- **Typing takes a pane back.** When another device has resized a pane, the first key you type brings it back to this Mac's size.
- **A pane that doesn't arrive says so,** with a Reload button.
- **Steadier connections.** A network change no longer drops a working connection to a server.
- **Large images show a placeholder** instead of nothing.
- **A click while a terminal comes back** now waits for it instead of being lost.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.2.0

Feedback that can carry a diagnostic log, and closing that asks where you clicked.

- **A diagnostic log with your feedback.** Send Feedback can include a log that helps us find a problem. It never holds what's in your terminals, your names or your paths, and What's included shows it to you before you send.
- **A report ID to quote.** After you send, Shepi shows an ID you can give to support.
- **Closing asks where you clicked.** Closing a tab or a space asks right next to it and shows exactly what will close.
- **Shepi works in Pi** without an error at start.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.1

Quicker, calmer alerts, and a new worktree that needs no name.

- **"Needs you" rings at once.** The sound and banner come as soon as an agent needs you.
- **"Done" means done.** An agent pausing between steps no longer rings as done.
- **Sounds from Herdr's app.** If you chose custom sounds in Herdr's desktop app, Shepi plays them too.
- **New worktree, no name needed.** The branch field comes with a name ready. Press Return to use it, or type your own.
- **An agent in error needs you.** Shepi shows it the same way as any agent that needs you.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.0

A web page as a pane, a clean-up for the worktrees your agents leave behind, and a window that keeps drawing.

- **A page beside the agent.** When an agent shows you a page, it opens as a pane next to its terminal, with Back, Forward and Reload. You can also open one yourself from a link's menu or the pane menu.
- **Worktree clean-up.** View › Worktrees… (⌥⌘W) lists every worktree on this Mac and your servers and tells you what each one still holds. Remove All Safe removes only the ones with nothing to lose.
- **The window keeps drawing.** An agent you were watching no longer freezes when another app sits over Shepi.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.0.3

The first release. Shepi is a native Mac app for [Herdr](https://herdr.dev). It shows every coding agent you run, on this Mac or on your servers, in real terminals in one window, and the one that needs you turns amber.

- **Everything where you left it.** When you open Shepi, every space, tab and agent Herdr is running is there. When you quit, Herdr keeps them going.
- **The agent that needs you.** It turns amber in the sidebar and the pane, with a banner and a sound. Press ⌃B a to go straight to it.
- **What you missed.** Everything that finished, needed you or asked a question while you were away waits in the inbox until you look.
- **Your other machines.** Add any machine you reach over SSH, and its spaces and agents join the sidebar.
- **Your agents can use Shepi.** An agent can ask you a question with buttons, show you a page, a file or its changes, report its progress, and open panes beside its own.
- **Group, filter and pin agents.** Group the Agents list by machine or space, show only what you want to see, and pin the agents you watch to the top.
- **Your Mac's permissions, for your agents.** Give Shepi Screen Recording or Accessibility once, and the agents in its panes have it too.
- **Panes and tabs.** Split, zoom, even out and swap panes, or drag one to another tab.
- **Find.** ⌘F searches agents, spaces, panes, machines and recent output on every machine.
- **Back in one key.** ⌘E lists the panes you used last, and Return takes you back to the one you just left.
- **Macros.** One key types the steps you wrote into the agent you're in.
- **Links and files.** ⌘-click opens a link, a server's dev site opens on your Mac, and you can paste screenshots or files into an agent on another machine.
- **Herdr plugins** work in Shepi.
- **Git at a glance.** The status line shows the branch of the pane you're in, and one click shows what the agent changed.
- **Tell us.** Send Feedback is in the sidebar and in Help, and Shepi is also [on GitHub](https://github.com/wio-apps/shepi).

Needs macOS 14 or later and Herdr 0.9.3 or later. Try it free for 14 days, then buy it once for $19.99, with every update included, on all your Macs. New to it? Start with the [guide](https://shepi.app/guide).
