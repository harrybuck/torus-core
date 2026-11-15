# Changes since build d3fc051 (14 November 2026)

From a second round of test installs on a fresh Windows computer. It upgrades in place and keeps your data, Twins, memory, chats and sign-ins.

- **One Claude sign-in for every Twin.** Sign in to Claude once, on its own page in Settings, and every Twin uses it, including ones you create later. It lasts a year, and the page tells you when to renew. Before, each new Twin needed a sign-in of its own and failed its first message without one.
- **Settings opens with Get started.** One row for each AI, with a plain status and one button for the next step, and Git shown only on Windows when Claude Code needs it. Once you're set up it shrinks to one line. Everything technical (the full checks, harnesses, usage, projects, automation and schedules) is folded under **Advanced** at the bottom.
- **Installing your AI talks to you.** The Install button answers the click at once, and the page moves on by itself when the installer finishes, straight to signing in. Nothing asks you to press Recheck.
- **A new Twin opens in a chat.** Creating a Twin takes you into a room with it, named after it, ready for your first message. Install-Buddy links straight to the Create a Twin form.
- **Signing in for the first time says so**, rather than asking you to "reconnect".
- **Windows download:** the README and the installer now steer you past the browser's "Open file", which only looks inside the zip, to Extract All.

If you already signed in to Claude for each Twin, nothing breaks; signing in once on the new page simply covers them all.

# Changes since build 9c693a2 (13 November 2026)

A small update from a test install on a fresh Windows computer. It upgrades in place the same way as below.

- **No terminal needed for your AI.** The Setup page now has an **Install Codex** button beside **Install Claude Code**, so whichever plan you have, Claude or ChatGPT, the Torus installs the AI for you and you sign in with a button. The README now says so up front, and keeps the manual steps in a fallback section near the end.
- **A clearer Setup card.** The Install button now stands where "missing" used to be, Sign in appears once, both look like buttons rather than warnings, and each AI's row talks only about that AI.
- **The installer shows its progress.** Each stage gets its own line, with dots while it waits for the Torus to start, instead of a silent cursor that looked like a hang.
- **The installer no longer contradicts itself** by saying "No folder to choose" straight after asking where your data should live.

# Changes since build 50c6e81 (3 November 2026)

This is a cumulative update for Windows 10/11, Apple-silicon Macs and Intel Macs. It upgrades in place and keeps your data, Twins, memory, chats and sign-ins. You can go straight to it from 50c6e81 or any earlier build; changes from earlier builds are listed further down and are included. A fresh installation needs nothing from this section: follow the package README.

Something wrong or confusing? [Open an issue](https://github.com/harrybuck/torus-core/issues/new) and say what you did and what you saw.

## How to upgrade

1. Let any running Twin replies finish. The installer stops the Torus for a minute while it upgrades.
2. **Windows:** download the Windows zip, right-click it and choose **Extract All**, then run **install.cmd** from the extracted folder (it may show simply as **install**). **Mac:** download the archive for your Mac (Apple silicon or Intel), unpack it, and open **Install Torus.command**. This is still an unsigned beta; the package README explains the operating system's opening prompts.
3. The installer should say it found your Torus and will **upgrade** it. If it offers a fresh installation instead, stop and tell us.
4. Keep the window open until it says **Torus upgraded from … to …**, then refresh your usual page.

If you use Grok Bots, re-orient each Bot once after upgrading, so it picks up the new standing rules.

## What you will notice

### Chats

- **Pictures of any size up to the 8 MB limit now send.** A photo over about 3 MB used to fail with "Maximum call stack size exceeded".
- **Re-orient answers the click at once.** The button changes to **Starting…** while the Torus prepares the new session, and a second press does nothing, so an impatient double-click cannot start two orientations.

### Capture and the Library

- **Capture stays put.** After you capture something, the page comes back empty and ready for the next one, with a confirmation at the top, instead of opening the new note. Your phone's share sheet works as before.
- **Library and Capture tabs have their own icon**, a cracked lens, so they are easy to tell from Chats.
- **Tab icons show on dark tab bars.** Both icons now sit on a small white tile. On the page itself, the Torus logo is bare ink on a light page and the tile on a dark one.

### Your Twins

- **Twins are told to look in the Torus before asking.** When you mention something specific a Twin doesn't recognise, such as a name, a book or an earlier decision, its standing rules now say to search your Library and past conversations before asking which one you mean.

### Grok Bots

- **Far fewer false "hasn't filed" warnings.** Grok runs background checks for each Bot that talk to the Torus without saying anything to you. Those checks now close themselves off, and the warning you see counts only work that changed something, not lookups.
- **A re-orient refreshes the Bot's saved rules**, so new rules last through a long chat instead of fading at the next compaction.

# Changes in build 50c6e81, since build 401d926 (23 October 2026)

This is a cumulative update for Windows 10/11, Apple-silicon Macs and Intel Macs. It upgrades in place and keeps your data, Twins, memory, chats and sign-ins. You can go straight to it from 401d926 or any earlier build; changes from earlier builds are listed further down and are included. A fresh installation needs nothing from this section: follow the package README.

## How to upgrade

1. Let any running Twin replies finish. The installer stops the Torus for a minute while it upgrades.
2. **Windows:** download the Windows zip, right-click it and choose **Extract All**, then run **install.cmd** from the extracted folder (it may show simply as **install**). **Mac:** download the archive for your Mac (Apple silicon or Intel), unpack it, and open **Install Torus.command**. This is still an unsigned beta; the package README explains the operating system's opening prompts.
3. The installer should say it found your Torus and will **upgrade** it. If it offers a fresh installation instead, stop and tell us.
4. Keep the window open until it says **Torus upgraded from … to …**, then refresh your usual page.

Nothing needs to be set up again. Your Twins pick up the new commands and skills at their next re-orient.

## What you will notice

### Your Twin can use Grok as well

- **Grok Bots are a new kind of Twin seat.** If you use the Grok Bot app, a Twin's page now has a **Grok Bots** section under Harnesses. **New Bot** makes one for one of the Twin's projects, and **1st prompt** gives you a single message to paste into Grok: the Bot connects itself to your Torus, saves its instructions and orients as your Twin. Each Bot has its own key, which you can revoke.
- **A Bot is your Twin, not a stranger.** It orients from the same memory, has the same Torus commands, and files every turn back into the Twin's memory, so what you discuss in Grok is remembered in his other rooms too.
- **Bots can read and post in your Twin's rooms**, address each other and other Twins, and answer messages left for them. A Bot that keeps working without filing its turns raises a reminder in your rooms after six hours.
- **Before a Bot re-orients, it is asked to file any turns not yet saved**, so the new orientation includes them.

### Email

- **Any mail provider works**, not just Gmail: on a Twin's page, choose **Own account** and enter the provider's IMAP and SMTP hosts and an app password (for Fastmail, `imap.fastmail.com` and `smtp.fastmail.com`).
- **A Twin can look through his own mailbox** when he needs to, for example for mail that arrived in another room. Looking marks nothing as read.
- **Word and Excel attachments open as text** for the Twin, as PDFs and text files already did.

### The Library

- **New skills for your Twin:** anchors and bridges (draw the ideas out of a note and connect them to your existing Ideas, one proposal at a time for your approval), link (both in one go), write (save part of a conversation as a note), research, council (five advisors on a decision) and quiz (a recall quiz on what you recently read), alongside the existing deep summary. Ask for them in plain words, such as "link this note" or "council this decision".
- **Ideas you approve are filed properly:** the idea, its source and your decision are recorded together, and the Twin remembers what you have approved and turned down when proposing the next ones.
- **Memory search shows where a hit came from** and lets the Twin open the full conversation, and a Twin can open a picture you sent in a chat when he needs to see it.

### Memory you can trust

- **A conversation that fails to save to memory now says so** in every room, with a **Retry** in Settings → Automation, instead of failing silently.
- **A long conversation that carries on after it was summarised is summarised again** once it has been quiet for an hour.
- **Older sessions kept in a shared Claude folder now save correctly.**

### Scheduled tasks

- **A task whose result fails a check is retried with the reason**, and a failed manual run is retried before its next scheduled time, instead of waiting a day.

### Rooms

- **Twins can reach each other without a shared room.** A Twin addressed from elsewhere is woken in his own main room, and the message says who wrote.

# Changes in build 401d926, since build 455bf76 (8 October 2026)

This is a cumulative update for Windows 10/11, Apple-silicon Macs and Intel Macs. It upgrades in place and keeps your data, Twins, memory, chats and sign-ins. You can go straight to it from 455bf76 or any earlier build; if you are coming from before 455bf76, its changes are listed further down and are included.

## How to upgrade

1. Let any running Twin replies finish. The installer stops the Torus for a minute while it upgrades.
2. **Windows:** download the Windows zip, right-click it and choose **Extract All**, then run **install.cmd** from the extracted folder (it may show simply as **install**). **Mac:** download the archive for your Mac (Apple silicon or Intel), unpack it, and open **Install Torus.command**. This is still an unsigned beta; the package README explains the operating system's opening prompts.
3. The installer should say it found your Torus and will **upgrade** it. It should not ask you to create a Twin or choose a data folder. If it offers a fresh installation, stop and tell us.
4. Keep the window open until it says **Torus upgraded from … to …**. Your browser or phone may disconnect while the Torus restarts.
5. Refresh your usual page. Everything should be where you left it. If a Twin's sign-in has expired, Settings shows a red **Sign in** pill that takes you straight to reconnecting it.

Nothing needs to be set up again after this upgrade. The one-time enrichment fix described for 455bf76 is no longer needed: background work now simply uses your Twin's own working chat setup (see below).

## What you will notice

### Scheduled tasks no longer interrupt your chat

- **A scheduled request now runs in its own room.** The first time one of a Twin's tasks comes due, the Torus creates a room called, for example, **TUUNBAQ SCHEDULED**. The task runs there as a real turn, with the Twin's full tools and memory, so he still remembers doing it. Your own conversation is no longer interrupted.
- **The result arrives as a Library note and an alert.** The Twin's reply is filed in the Library Inbox, titled with the task and date. A lingering alert appears in that Twin's rooms, **"⏰ … finished. Open note"**, until you open the note or dismiss it. A run that fails shows a red alert with the reason instead.
- **Reminders no longer wake the Twin.** A reminder-type task now simply shows its text as an alert.
- **Task times read normally**, for example "every 30 days" rather than "every 43200 minutes".

### Email goes to the right room

- **Replies to a Twin's email return to the room that sent it.** If your Twin emails you from one project's chat and you reply, your reply arrives in that same chat.
- **You choose where new email lands.** Each Twin's page in Settings has a **New mail goes to** choice under Email. The default is his most recently used room, which is how it worked before.

### Projects

- **Creating a project needs only a name.** Pick the Twin (skipped when you have only one) and, optionally, name its first chat; the suggestion is the Twin plus the project, such as "Tuunbaq Book2". The Torus creates the project's working folder itself. **Use an existing folder…** connects files you already have, without moving them.
- **Renaming a project** changes only its name; its files, chats and memory stay put.
- **A new project starts with everything the Twin already remembers.** Later conversations stay in the new project, and all of a Twin's projects automatically see brief updates from one another. This also applies to projects you already have, with nothing to configure. If you want a complete wall between two pieces of work, use two Twins.
- **Deleting a Twin now asks properly.** A separate page lists what will be removed and asks you to type the Twin's name. Previously the Delete button could act without asking.

### Chats

- **Every message shows its turn number** (TURN 529, for example). A Twin's reply carries the number of the turn it answers. Twins now see these numbers on new messages, so "what you said in turn 529" works for recent turns.
- **The Re-orient menu is clearer:** Model, Packet size (Small, Medium, Large, X-Large) and Context impact on separate labelled rows. A **Harness updates available** link appears only when an update is waiting.
- **The context warning** shows how many times the session has been compacted and suggests Re-orient, in calmer wording.
- **The model menu shows every model your installed Claude Code and Codex support.** Before, a restart could leave it showing an older Codex's list.

### Settings

- **Harness updates and Usage** are tidied into cards like the rest of Settings.
- **The Gmail app-password steps** are spelled out beside each Twin's email settings.

### Background work and memory

- **Background work uses your Twin's own working setup.** Memory summaries, Library enrichment and routines use the same model, harness and sign-in as that Twin's last successful chat. There is no separate background account to keep signed in. With one personal Twin this is automatic; with several, Settings has one **Default Twin for automation** choice for shared work.
- **This should fix enrichment on Codex-only computers** without any setting changes, and memory summaries no longer stall behind an expired background sign-in. If enrichment still fails after upgrading, check that **Default Twin for automation** (Settings → Automation) names the Twin you chat with.
- **A blocked memory job names the Twin** and links to Reconnect. Background runs never become part of a Twin's conversation memory.

### X-Digest (only if you use it)

- X-Digest recovers from temporary connection failures and processes large digests in saved batches, so a long backlog survives restarts.
- A faster X collector exists but is **off unless you add it**. Upgrading does not turn it on or change your X usage.

## Validation and limits

The application suite passed 914 tests with no failures (nine package-dependent tests are skipped in a developer run), and the memory engine's 127 checks passed. Each new behaviour in this build was also checked by deliberately breaking it and confirming a test failed. These changes were developed and run day to day on a Mac. The Windows package is built and verified file by file, but this build has not yet been run on a Windows computer by us, so Windows users are the first to try it there. This beta is not yet code-signed.

# Already in build 455bf76 (for anyone upgrading from 3484a77 or earlier)

## Fixes

- **Enrichment on Codex-only installations.** New automatic background choices use installed harnesses enabled for the Twins. Enrichment chooses a compatible personal Twin rather than permanently retaining Install-Buddy; memory processing and reflection use the same harness-selection rule. Explicit settings remain explicit.
- **Failed captures can be recovered without recapturing.** A missing harness executable is no longer mistaken for a missing note. Unavailable harnesses and sign-in failures hold affected jobs with an explanation instead of repeatedly trying or cancelling them. Settings validates the selected harness/Twin combination; model and Twin can be changed together before saving. Previously cancelled captures now have Retry controls.
- **New captures cannot inherit a deleted note's processing job.** Each new capture gets an independent identity. Retried deliveries still retain their existing receipt so they do not create duplicate notes.
- **Expired Codex usage readings no longer cause warnings.** After a usage window resets, its old percentage disappears from the warning and Harnesses heading until a fresh reading arrives.
- **Re-orient buttons agree while a turn is running.** The button in the context warning is disabled while the room is busy, just like the main Re-orient control.
- **Library headings match Chats.** Library title pills now use the same lighter label styling as Chats, with the constant prefix **TORUS LIBRARY - ** before the room or note title. The Library index keeps its short title; narrow screens hide the prefix to leave room for the title itself.

## New and changed

- **Read a source without adding it to the Library.** Twins have a read-only MCP tool using the same extractor as Library enrichment. They can read available YouTube transcripts, web articles, PDFs and text URLs, then discuss them with you without capturing and later deleting a note. Long sources are read in chunks. Missing or blocked captions remain an extraction failure, not a licence to invent a summary.
- **AI tool update notices and user-approved updates.** The Torus checks Claude Code and Codex releases daily, offers Check now, and shows version information and identified new-model announcements in Settings. Relevant chats get a brief Review/Later notice. You choose whether to install; supported updates wait for idle time and refresh the model catalogue afterward. Desktop/editor-bundled tools may require their application's updater. Announced models are not a guarantee of access on every account.
- **Quieter context reminders.** The large reminder lasts for one turn rather than remaining permanently visible. Claude gets the near-capacity reminder; Codex waits until at least two compactions have occurred, on the third approach to capacity. The normal context indicator remains available.
- **Restart Torus in Settings.** Settings → Status has a Restart Torus control with confirmation and browser recovery. Installed services supervise the restart, including on Windows. Running work is interrupted; a Torus restart does not restart Tailscale or fix network connectivity.
- **Incoming email can be pinned to a chosen private room.** An explicit per-Twin routing setting prevents mail from drifting into another project room. If that pinned room is closed or unavailable, delivery waits rather than going elsewhere. This release does not add a room-picker UI for that setting.

## How to upgrade, and what to expect

You can go straight from build 3484a77 or another earlier build to this release. Use the same computer and user account; do not uninstall the Torus or remove its data folder.

1. Let active Twin turns and other work finish. The installer stops the Torus briefly during the upgrade.
2. **Windows:** download the Windows zip, right-click it and choose **Extract All**, then run **install.cmd** from the extracted folder (it may appear simply as **install**). **Mac:** download the Apple-silicon or Intel archive for your computer, unpack it, and open **Install Torus.command**. This is still an unsigned beta; the package README explains the operating system's opening prompts.
3. The installer detects the existing Torus and says it will upgrade. It should not ask you to create new Twins or select a new data folder. Stop and report it if it unexpectedly offers a fresh installation.
4. Keep the installer window open until it reports **Torus upgraded from … to …** and the number of files checked before and after. The browser and phone may disconnect while the application restarts.
5. Reopen your usual bookmark or refresh the page. Your Twins, chats, Library and sign-ins remain. You do not need to repeat onboarding; a provider may still ask you to reconnect an expired sign-in. Retry any chat message that had already failed.

The upgrader refreshes application files, Twin tool wiring and Install-Buddy's generated instructions. It retains the previous application until the next upgrade and attempts to restore it if replacement fails. If an error appears, save the message and ask for help rather than deleting data or starting over.

**For Boro and other Codex-only installations with failed enrichment, the following setting correction and retries are still needed after upgrading.** Updating the application does not silently overwrite an old saved Claude choice.

## One-time recovery for older enrichment settings (not needed from the next build on)

An old saved Claude choice is not automatically overwritten: earlier versions did not record whether it was chosen by the user or written as a default.

1. Open Settings → Enrichment. On a Codex-only computer, choose an available Codex model and a Twin with Codex enabled, or choose Automatic for both fields.
2. Press Save changes.
3. Open Capture → Prior capture activity. Retry one cancelled or held note and check that it finishes, then retry the remaining affected notes. Keep the existing notes; there is no need to delete and recapture them.

If you already corrected these settings and successfully enriched a note, keep those working settings and retry only the remaining failed notes.

If upgrading from a build earlier than 3484a77, this also includes automatic separation from adopted old Obsidian folders, Copy me (Off/CC/BCC), copied-only email handling, and the corrected Library-search and Gmail app-password wording from that release.

## Published build validation and limits

The application suite passed 868 tests with zero failures (nine package-dependent tests were skipped in that run). All 18 deliberate breaks of the new background-selection and recovery rules were caught. Release packages are additionally checked during packaging. The Codex-only Windows scenario was covered by controlled fixtures; this is not a claim that the release has already run on Boro's computer. This beta is not yet code-signed.
