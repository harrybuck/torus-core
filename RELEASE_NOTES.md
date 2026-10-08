# Torus beta — build 455bf76

# Changes since build 3484a77 (30 September 2026)

This is a cumulative update for Windows 10/11, Apple-silicon Macs and Intel Macs. Install it the same way as the earlier build: it upgrades in place and retains your data, Twins, memory and sign-ins. You can skip intermediate builds.

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

## One-time recovery for older enrichment settings

An old saved Claude choice is not automatically overwritten: earlier versions did not record whether it was chosen by the user or written as a default.

1. Open Settings → Enrichment. On a Codex-only computer, choose an available Codex model and a Twin with Codex enabled, or choose Automatic for both fields.
2. Press Save changes.
3. Open Capture → Prior capture activity. Retry one cancelled or held note and check that it finishes, then retry the remaining affected notes. Keep the existing notes; there is no need to delete and recapture them.

If upgrading from a build earlier than 3484a77, this also includes automatic separation from adopted old Obsidian folders, Copy me (Off/CC/BCC), copied-only email handling, and the corrected Library-search and Gmail app-password wording from that release.

## Validation and limits

The application suite passed 868 tests with zero failures (nine package-dependent tests were skipped in that run). All 18 deliberate breaks of the new background-selection and recovery rules were caught. Release packages are additionally checked during packaging. The Codex-only Windows scenario was covered by controlled fixtures; this is not a claim that the release has already run on Boro's computer. This beta is not yet code-signed.

Packaging verification for this build: all 34 installer/package checks passed with no skips. Every manifest-listed file was verified in the Windows, Apple-silicon and Intel packages; SHA-256 checksums accompany the downloads.
