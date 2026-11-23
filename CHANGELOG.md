# Release notes

Every version of Shepi for Herdr, newest first. The same notes are at [shepi.app/releases](https://shepi.app/releases).

## Shepi 1.5.1

Worktrees tells what you would really lose.

### Fixed

- **A generated Xcode project no longer holds up a worktree.** When a worktree's only extra files are an Xcode project that your project's generator makes again, Worktrees marks it Safe and ticks it for removal, instead of asking you to take a look.
- **A link is not counted as work.** A link in a worktree to a file or folder elsewhere, such as your main checkout’s secrets, no longer makes it read as uncommitted. Removing it takes only the link, never what it points to.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.5.0

Agents reach you, show you their plans and pages, and make you mods.

![Shepi with a plan beside its agent and a mod on the right](guide/img/release-1.5.0.webp)

### New

- **Speak instead of typing.** Hold ⌥ and talk, and your words are typed in the pane in front of you or in any other app. Hold ⌥ ⌃ and they are typed in English, or another language you choose.
- **Capture your screen.** Press ⌃⌘A and drag, and ⌘V pastes the picture at once. It works in every app on your Mac, even with Shepi quit. A row under it lets you mark it where it is, copy the words in it or save it, a key each. Point at a pop-up, a pane or a sidebar and it is taken on its own. The words you copy out of it come as they stand, line for line, and a translation lands on the picture itself, where the original was — both send the picture to be read, and Shepi asks you the first time. Private details, such as an email or a key in a terminal, are covered with masks before you share it. ⌃⌘L takes something longer than the screen while you scroll, and ⌃⌘R records.
- **Keys on screen.** Turn it on and the key you just pressed is named at the bottom right of your screen, with what it did — for a recording, a demo, a lesson, or while you are still learning your own keys. Only Shepi's own keys are ever named: what you type, what you say and what you do in other apps are never on it. Drag the strip wherever you want it.
- **One clipboard for the accounts of your Mac.** Copy in one account and paste in another: text, pictures, files and whole folders. Passwords are never shared, and nothing leaves your Mac.
- **Agents reach you.** Ask an agent to let you know, and its words reach you on your Mac and on your iPhone. A click takes you to its pane, where you answer.
- **Files open beside your agent.** An agent can show you its plan or any other file right next to it. Markdown reads like a page, with its code and diagrams drawn, and you can edit and save it there.
- **Agents use the page they opened.** An agent uses the web page in its pane as you would: it reads, clicks, drags, types, attaches a file and signs in, and you watch it happen. A click on the green dot in the page's header takes you to that agent. Several pages share one pane, a click apart, so each has room to read.
- **Pin a capture to your screen.** Press Pin on the row under a capture and the picture stays where you took it, over every app, while you work. Drag it anywhere, make it bigger or fainter, and hold one thing against another.
- **Private panes, files and downloads in a page.** Open a page in a private pane to see it signed out. Choose File now works in a page, and what you download is saved in Downloads, with a notification when it is done.
- **Mods.** Ask an agent for a mod on the right of the window, such as your usage or a release you are waiting for. It stays there in every space; pause one from its menu when you don't need it, and click its title to fold it. ⌥⌘B shows or hides them.
- **Leave a job for later.** Tell an agent to run something at a set time or when it is done. It starts in a new pane at that moment, even with Shepi closed.
- **Sub-agents under their agent.** When Claude Code or Codex starts helpers, they appear under its name while they run, with when they started and how long they have been running.
- **Your agents in your order.** They follow the window's order, so agents in one tab sit together. Group them by project, tab, space or machine, tell an agent how to arrange them, or drag a space or an agent where you want it.
- **Agents see what you see.** An agent can see what's in a pane it names, as it looks to you: a terminal, a file, a web page or a mod. It can also open or close the mods on the right for you.
- **Five macros to press from the start.** A new Shepi comes with five shortcuts for Claude Code: its effort to medium, high or xhigh, and its model to Opus or Fable, each for that session only. They are yours from then on — read their steps, rewrite them, give them other keys or delete the ones you don't want.
- **Monthly or yearly.** Shepi is now a subscription, and you can have your money back within a week by asking. On monthly, you can switch to yearly from Settings at any time.

### Improved

- **Shepi keeps working after you quit it.** Quitting frees what its window used, while the menu bar keeps notifications, mods, speaking, capture and the shared clipboard going. Quit Completely in the menu bar stops it all.
- **Your marking stays as you left it.** The tool, the colour and the weight you used last are in your next capture, so you mark a screenshot without choosing anything first.
- **One scroll on the right.** Scrolling over a mod that is taller than its card carries on into the column the moment the mod reaches its end, in the same movement, so one scroll moves what you meant.
- **Long task names you can read.** An agent's task list keeps its size; scroll a long name sideways with the mouse or trackpad to read all of it.
- **Lighter on your Mac.** A working agent's green dot now stands still, so Shepi draws nothing while your agents work.
- **A calmer sidebar.** Each space takes one line with only its state at the right, and computers are quiet labels above their spaces. A working agent shows a green dot.
- **Tabs show their agents.** A tab shows whether an agent in it is working, needs you or is done.
- **Find is easier to read.** Each result takes one line, with where it is at the right. Tab narrows the results to agents, panes, output or another kind.
- **Choose what the window shows.** Settings › Appearance › Show has a switch for each small thing on agent rows, tabs, pane headers and the status line, and a right-click on any of them gives the same switches. An agent can set them for you.
- **Changes shows only the files that changed,** and its counts match the status line.
- **A waiting agent's pane glows.** When an agent needs you and its pane is on screen, the pane itself glows softly instead of a card in the sidebar.
- **Zoom in pages and files.** ⌘+ and ⌘− make a web page or a file bigger or smaller, and a diagram opens on its own, larger.
- **Diagrams drawn as in VS Code.** Mermaid diagrams in a file are drawn the way VS Code draws them, easy to read on the dark window.
- **Notifications follow what you are doing.** Notify Me now offers In Another App, Always and Never. Always reaches you wherever you are looking, even while you are in Shepi, where macOS keeps it in Notification Center, and you still hear one sound.
- **A macro runs with one shortcut.** You press its keys once, with nothing to press first. A macro that was on a key after the prefix moves to a free shortcut, and Shepi tells you which.
- **Shepi's name in the title bar.** Its diamond turns amber while any agent needs you, and a click on it opens Shepi's website.
- **Macros pick by name.** A macro finds a menu's row by what it says and checks that it worked; if anything isn't as expected, it stops and tells you why, so an update to your agent can't make it pick the wrong thing.
- **A slow machine says so.** When another machine is slow to answer, its name says so, and Check Connection… finds why and how to fix it.
- **What each space has to push and pull** shows on its row.
- **Quit Completely has its own shortcut,** ⌥⌘Q.
- **If speaking can't connect,** it tells you, and keeps what you said for Try Again.

### Fixed

- Settings shows whether Full Disk Access is really on.
- An agent always reaches the Shepi that shows its machine, and is never told Shepi is closed while it is open.
- A click clears a selection in a pane, also in a program that uses the mouse.
- A click on a space selects it again.
- A pane dragged to another tab lands where its preview showed it.
- A file another Mac keeps from remote logins now says why it can't be opened, and how to allow it.
- Copying in Vim on another machine reaches your Mac, and a drag that Vim takes for itself tells you how to select instead.
- Done banners stay long enough to read.
- A mod whose page is taller than its card shows that there's more.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.4.2

Smoother scrolling, and agent cards and settings that respond the way you expect.

### Fixed

- **Scrolling stays smooth while an agent works.** Scrolling through an agent that is busy no longer stops for a moment now and then.
- **Agent cards close when you're done with them.** A card that opened while the pointer rested on an agent now closes when you move away from it or click somewhere else.
- **The size buttons answer every click.** In Settings › Appearance › Size, the − and + buttons work wherever you click on them.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.4.1

Agents reach Shepi reliably, and every answer and setting stays where it belongs.

### Fixed

- **Agents reach Shepi whenever it's open.** They no longer say Shepi isn't open while it is.
- **Codex and Grok Build keep your settings.** Shepi no longer removes settings you chose in Codex or Grok Build.
- **Every answer reaches its own question.** Your answer always goes to the question you answered, and an agent that asks the same question again right away gets a new card.
- **Permissions as they are now.** When an agent asks whether Shepi has a permission, it hears what is turned on now, even if you just changed it in System Settings.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.4.0

Your agents use Shepi on their own, every question waits in one card, and Shepi speaks Japanese and Chinese.

### New

- **Your agents use Shepi on their own.** Claude Code, Codex and the other agents find Shepi among their tools, with nothing to set up. Ask for a page "on your right" or tests "next to you", and the agent does it.
- **Agents hand work on to fresh agents.** When an agent finishes, a fresh one can start with the next task, right away or at a time you choose, even with Shepi closed.
- **See what an agent is working on.** Its current step and how far along it is show under its name, and a click shows the whole task list.
- **Answer your agents from anywhere.** Every question from every agent waits in one card at the top right, without getting in your way. Answer with a key, in your own words, or with a screenshot or files. A question waits through a restart of Shepi, and your answer still reaches the agent.
- **See what an agent wants to run.** When an agent stops to ask permission, its row shows what it wants to do.
- **Shepi in Japanese and Chinese,** following your Mac's language or the one you pick. shepi.app has both too.
- **Send a pane to the background.** It keeps running, and the tray beside Find brings it back.
- **Panes on any side.** Agents can open panes above, below, left or right of themselves, and you can split a pane from its header and resize the sidebar.
- **Every machine in its own colour,** so you always know where an agent runs.

### Improved

- **Notifications say which agent** and what happened. Click one to go to its pane.
- **The Agents list stays put.** Rows no longer jump around as agents change state, and you can sort and pin them.
- **Changes in a card over your panes.** It stays open as you move between panes, and undoing a change can itself be undone.
- **Settings, reorganized,** so each setting is where you'd look for it, and search finds any of them.
- **Easier to read, calmer to look at.** Larger text in the Mac's own font, a faint line between the sidebar's rows, and no scroll bars.
- **Macros.** Your agent can write them for you, and a macro can now press ctrl, alt and shift with any key.
- **Shepi reopens where you were,** on the same machine, space, tab and pane.
- **Closing a tab shows the next one.**
- **Worktrees and Git in one place.** The worktree list ticks the safe ones for you, and the status line's Git part shows what changed and what's left to push.
- **Lighter on your Mac,** especially while agents are busy.

### Fixed

- Scrolling stays smooth while a program prints.
- Copying in a pane on another machine reaches this Mac's clipboard.
- A question no longer shows twice or comes back after it was withdrawn.
- Esc leaves copy mode at once, and Shepi opens normally when the Mac is offline.
- Terminals in view keep drawing when macOS wrongly thinks Shepi's window is covered.

Needs macOS 15 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.3.0

A brighter sidebar that tells you more at a glance, a roomier worktree list, and typing that takes a pane back.

### New

- **Push and pull at a glance.** Each space shows how many commits are waiting to be pushed and pulled.
- **Space tiles you can tell apart.** Each space has a tile in its own colour with a letter or an emoji.
- **⌘B shows and hides the sidebar.**

### Improved

- **Agents lead with their own mark.** Each agent row starts with its maker's mark, and its state sits on the right.
- **A tidier sidebar.** Spaces and agents line up, with one badge for each state.
- **A roomier worktree list.** It opens in the middle of the window, and Shepi remembers the size you give it.
- **Typing takes a pane back.** When another device has resized a pane, the first key you type brings it back to this Mac's size.
- **A pane that doesn't arrive says so,** with a Reload button.

### Fixed

- **Steadier connections.** A network change no longer drops a working connection to a server.
- **Large images show a placeholder** instead of nothing.
- **A click while a terminal comes back** now waits for it instead of being lost.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.2.0

Feedback that can carry a diagnostic log, and closing that asks where you clicked.

### New

- **A diagnostic log with your feedback.** Send Feedback can include a log that helps us find a problem. It never holds what's in your terminals, your names or your paths, and What's included shows it to you before you send.
- **A report ID to quote.** After you send, Shepi shows an ID you can give to support.

### Improved

- **Closing asks where you clicked.** Closing a tab or a space asks right next to it and shows exactly what will close.

### Fixed

- **Shepi works in Pi** without an error at start.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.1

Quicker, calmer alerts, and a new worktree that needs no name.

### New

- **Sounds from Herdr's app.** If you chose custom sounds in Herdr's desktop app, Shepi plays them too.

### Improved

- **"Needs you" rings at once.** The sound and banner come as soon as an agent needs you.
- **New worktree, no name needed.** The branch field comes with a name ready. Press Return to use it, or type your own.

### Fixed

- **"Done" means done.** An agent pausing between steps no longer rings as done.
- **An agent in error needs you.** Shepi shows it the same way as any agent that needs you.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.1.0

A web page as a pane, a clean-up for the worktrees your agents leave behind, and a window that keeps drawing.

### New

- **A page beside the agent.** When an agent shows you a page, it opens as a pane next to its terminal, with Back, Forward and Reload. You can also open one yourself from a link's menu or the pane menu.
- **Worktree clean-up.** View › Worktrees… (⌥⌘W) lists every worktree on this Mac and your servers and tells you what each one still holds. Remove All Safe removes only the ones with nothing to lose.

### Fixed

- **The window keeps drawing.** An agent you were watching no longer freezes when another app sits over Shepi.

Needs macOS 14 or later and Herdr 0.9.3 or later. Shepi finds the update itself, or ask for it in Shepi › Check for Updates.

## Shepi 1.0.3

The first release. Shepi is a native Mac app for [Herdr](https://herdr.dev). It shows every coding agent you run, on this Mac or on your servers, in real terminals in one window, and the one that needs you turns amber.

### New

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
