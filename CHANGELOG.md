# Release notes

Every version of Shepi for Herdr, newest first. The same notes are at [shepi.app/releases](https://shepi.app/releases).

## Shepi 1.3.0

A brighter sidebar that tells you more at a glance, a roomier worktree list, and typing that takes a pane back.

- **Each space shows what it has to push and pull.** After the branch, ↑ counts the commits to push and ↓ the commits to pull, in the branch's own quiet colour. Nothing shows when the branch is even or has no upstream.
- **Space tiles you can tell apart.** Each space's tile is now a solid colour with a white capital letter, or the emoji its name starts with. The colours stay clear of amber, green, red and the working blue, so a tile never looks like a state.
- **Agents lead with their own mark.** Each agent row starts with its maker's mark in the maker's colour: Claude Code in terracotta, Gemini CLI in blue, and so on. The state moved to the right of the title: a spinner while working, a check when done, a ring when idle. "needs you" keeps its amber pill. The agent's name is in the mark's tooltip and in VoiceOver.
- **One look for every sidebar row.** Space rows and agent rows are the same height and line up. A space's counts are round badges, one per state, and an agent's state is the same mark without a number.
- **⌘B shows and hides the sidebar.** If you set your own key for it, Shepi keeps yours.
- **The worktree list is wide and short.** It opens in the middle of the window, 760 pt wide and only as tall as its rows. Drag any edge or corner to resize it; Shepi remembers the size.
- **Typing takes a pane back.** When another device has resized a pane, the first key you type gives it back to this Mac's size, with no note in the way.
- **A pane that doesn't arrive says so.** If a pane stays empty for 30 seconds after its machine connects, it says "This pane didn't arrive" with a Reload button, and the machine's other panes carry on.
- **Steadier connections to your servers.** A network change no longer drops a working SSH session: Shepi checks that it still answers before replacing it.
- **Large images show a placeholder.** An image too large for the terminal to keep shows its size in the space it would take, instead of nothing.
- **A click while a terminal comes back** now waits for it instead of being lost.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.2.0

Feedback that can carry a diagnostic log, and close questions that ask where you started.

- **A diagnostic log with your feedback.** Send Feedback can now include a log of what Shepi was doing: connection states, requests by method, notification decisions and a summary of each recent crash. It holds neutral labels such as "space 1 › tab 2", never terminal contents, names or paths. The switch is on by default and remembered, and What's included shows you the log before you send.
- **A report ID to quote.** After you send, Shepi shows an ID you can copy or put in an email to support. Settings › General keeps your last three.
- **A close asks where you started it.** Close a tab from its `×`, its menu or a middle-click and the card appears under that tab; Close Space from a sidebar row puts it beside the row. What will close is struck through right there, the arrow points at its name, and the card stays over your panes, clear of the sidebar. Closing by key still asks in the middle of the panes.
- **Shepi's agent skill loads in Pi.** Its description is now valid YAML, so Pi no longer lists it among its startup errors.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.1

Quicker, calmer alerts, and a new worktree that needs no name.

- **"Needs you" rings at once.** When an agent needs you, the sound and banner come straight away instead of after a delay.
- **"Done" means done.** A done alert waits a second and rings only if the agent is still done, so an agent pausing between steps stays quiet.
- **Sounds from Herdr's app.** If you set custom sounds in Herdr's desktop app, Shepi now plays them, unless your Herdr config names its own. Settings › Notifications says where each comes from.
- **New worktree, no name needed.** The Branch field opens with a generated name, as Herdr makes them, already selected. Press Return to use it or type your own.
- **An agent in error needs you.** When Herdr reports an agent in error, Shepi shows it as needing you, everywhere it shows that.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.0

A web page as a pane, a clean-up for the worktrees your agents leave behind, and a window that keeps drawing.

- **A page beside the agent.** An agent runs `shepi-agent show <url> --pane` and the page opens as a pane next to its terminal, in Shepi, with Back, Forward, Reload and Open in Browser in its header; a dev server on one of your servers is forwarded to your Mac first. You can open one yourself: Open as a Pane in a link's menu, Split Right with Web Page… in the pane menu, or, from a web pane, Split Right with This Page. The page keeps its own storage (Settings › Agents clears it) and gets no camera, microphone or files. Shepi's keys still work while it has the keyboard, and Esc hands the keyboard back.
- **Worktree clean-up.** View › Worktrees… (⌥⌘W) lists every worktree on this Mac and your servers with its branch, size, last activity and what it holds: merged, clean, unpushed commits, uncommitted changes, ignored files such as `.env`, an agent still there, a folder that's gone, or a folder Git doesn't know. Remove All Safe takes only the ones with nothing to lose, among the rows you're showing. Anything else needs its own switch, beside a line saying exactly what would be lost. Merged branches can go with their worktree; others are kept.
- **The window keeps drawing while you watch it.** macOS sometimes reported Shepi's window as fully covered while it was in plain sight (another app's invisible overlay was enough), and Shepi stopped asking Herdr for frames, so the agent you were watching froze mid-line. Now a window counts as covered only when other apps' ordinary windows really lie over it, and moving the pointer over the window counts as seeing it.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.0.3

The first release. Shepi is a native Mac client for [Herdr](https://herdr.dev): every coding agent you run (Claude Code, Codex, OpenCode, Gemini CLI, Cursor, Copilot CLI) in a real terminal, in one window, on this Mac or your servers, with the one that needs you in amber.

- **Everything where you left it.** Open Shepi and every space, tab and agent Herdr is running is there. Quit it, and Herdr keeps them going.
- **The agent that needs you.** It turns amber in the sidebar, the pane header and the status line, with a banner and Herdr's own sound. Two keys take you there (⌃B a).
- **What you missed.** Leave Shepi open and step away: every agent that finished, needed you or asked a question meanwhile waits in the inbox next to Find until you look, and the Dock icon shows how many.
- **Your other machines.** Add any machine you reach over SSH; it joins the sidebar with its spaces and agents.
- **Your agents can use Shepi.** An agent can ask you with buttons, show you a page, a file or what it changed, report its progress, and open panes beside its own, on this Mac or a server. Inside Claude Code's sandbox too, once you allow it in Settings › Agents.
- **Group, filter and pin agents.** Group the Agents list by machine or by space, show only the states or machines you pick, and pin the ones you watch to the top. One that needs you is never hidden.
- **Your Mac's permissions, for your agents.** Give Shepi Screen Recording or Accessibility once, and agents in its panes on this Mac have it too, through every update.
- **Panes and tabs.** Split, move between panes, even them out, zoom one, and drag a pane by its header to swap it, put it beside another or send it to another tab. A tab without a name of its own is named after its agent.
- **A new space by mouse.** Point at SPACES for a plus that makes one at once, or right-click below your spaces.
- **Find.** ⌘F searches agents, spaces, panes, machines and recent output, on every machine.
- **Back in one key.** ⌘E lists the panes you used last, newest first; Return takes you back to the one you just left, or type a few letters to pick another.
- **Macros.** One key types the steps you wrote into the agent you're in, waiting for each menu. Every macro is also a command in Find.
- **Links and files.** ⌘-click opens a link, and a dev server's localhost on a server opens on your Mac. Paste a screenshot or files into an agent on another machine.
- **Herdr plugins.** Their panes, popups and actions work in Shepi, and what they report shows in the sidebar.
- **Git at a glance** in the status line, for wherever the focused pane is working, worktrees included.
- **What the agent changed.** Click the changes in the status line (or press ⌃B d or ⇧⌘D) to read the diff beside your panes, split or unified, each file in its own language, on this Mac or a server.
- **Learn the keys as you go.** After a click, the status line names the key once. Settings has a search field, and Esc closes it.
- **Tell us.** Send Feedback is a button in the sidebar and in Help, and in public there's [Shepi on GitHub](https://github.com/wio-apps/shepi).

Needs macOS 14 or later and Herdr 0.9.3 or later. Try it free for 14 days (Shepi reaches shepi.app once to start the trial); $19.99 once, with every update included, on all your Macs. New to it? Start with the [guide](https://shepi.app/guide).
