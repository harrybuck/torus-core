# The Torus

A home for your personal AI Twin: a small program that runs on your own computer, keeps your Twin's memory in one folder you own, and opens in your browser. Your Twin works through an AI subscription you already have, Claude or ChatGPT; the Torus adds no cloud service of its own. You'll need a paid Claude or ChatGPT plan; the Torus's Setup page helps you install your AI.

This is a **beta**. Expect rough edges. When something goes wrong or confuses you, [open an issue](https://github.com/harrybuck/torus-core/issues/new) and say what you did and what you saw.

## Download (build 622a3de)

| Your computer | File | Then |
|---|---|---|
| Windows 10 or 11 | [torus-win-x64-622a3de.zip](https://github.com/harrybuck/torus-core/releases/download/beta-622a3de/torus-win-x64-622a3de.zip) | Use **Extract All** on this file, not **Open file**: the installer can't run from inside the zip. |
| Mac with Apple silicon (M1 or later) | [torus-mac-arm64-622a3de.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-622a3de/torus-mac-arm64-622a3de.tar.gz) | Double-click it to unpack, then right-click **Install Torus.command** and choose **Open** (this beta is not yet signed). |
| Mac with an Intel processor | [torus-mac-x64-622a3de.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-622a3de/torus-mac-x64-622a3de.tar.gz) | Double-click it to unpack, then right-click **Install Torus.command** and choose **Open** (this beta is not yet signed). |

Checksums: [Mac](https://github.com/harrybuck/torus-core/releases/download/beta-622a3de/SHA256SUMS-622a3de.txt) · [Windows](https://github.com/harrybuck/torus-core/releases/download/beta-622a3de/SHA256SUMS-win-622a3de.txt)

[Upgrade instructions and what to expect](#already-have-the-torus-upgrade-with-the-same-steps) · [Changes in each build](RELEASE_NOTES.md) · [Build 622a3de release page](https://github.com/harrybuck/torus-core/releases/tag/beta-622a3de)

## What you'll need

A paid **Claude** or **ChatGPT** plan, and nothing else to install first. After the Torus installs, its Setup page installs your AI for you (Claude Code for a Claude plan, Codex for a ChatGPT plan) and signs you in, with a button for each.

The Torus also works with **Grok Bots**, as an optional extra seat for a Twin: the same Twin, with the same memory, talking to you in the Grok Bot app. They come on top of Claude Code or Codex, not instead of them, because Grok cannot do the Twin's background memory work. A Bot reaches your Torus over the internet, so set up [phone access](#reach-the-torus-from-your-phone) first; then make a Bot from the **Grok Bots** section of a Twin's page.

## Install on Windows

1. Download the zip. In the browser's download list, **don't press Open file**: that only looks inside the zip, and the installer can't run from there. Press the folder icon beside it instead (or open your Downloads folder), then right-click the zip and choose **Extract All**.
2. In the extracted folder, open **Torus-Installer** and double-click **install**.
3. Windows may show a blue *Windows protected your PC* box, because this beta is not yet code-signed. Choose **More info**, then **Run anyway**.
4. Answer the two questions: your name, and where your data should live (press Enter for a Torus folder in your user folder).
5. Settings opens in your browser. On its **Setup** card, press **Install** for your AI (Claude Code or Codex), then **Sign in**. Then follow the banner to **Install-Buddy**, who confirms everything works and helps you create your own Twin.

**Moving from the Obsidian-era Torus?** Tell Install-Buddy. He finds your old vault, tells you what he found, and on your go brings the old conversations into your new Twin's memory and every note and idea into the Library. Nothing in the old vault is changed or deleted.

No administrator rights are needed. The Torus starts by itself when you sign in to Windows, and a **Torus** shortcut appears on your Desktop.

**If Windows refuses with no Run anyway button**, your PC has Smart App Control switched on, which is common on new Windows 11 computers. Open PowerShell and unblock the extracted folder, then double-click **install** again (type the folder name as it appears in your Downloads):

```
gci ~\Downloads\torus-win-x64-622a3de -r | Unblock-File
```

**No window while the Torus runs.** The Torus and its memory jobs run with no window on any account. If the Torus ever stops, the half-hourly memory job starts it again; `schtasks /run /tn "Torus Serve"` in PowerShell starts it at once.

## Install on a Mac

1. Download the archive for your Mac and double-click it to unpack.
2. Open the **Torus-Installer** folder it unpacks to and double-click **Install Torus.command**. It opens a Terminal window and runs the installer there.
3. If macOS says it can't be opened because the developer is unidentified (this beta is not yet signed), right-click **Install Torus.command**, choose **Open**, then **Open** again.
4. Answer the two questions. Settings opens in your browser. On its **Setup** card, press **Install** for your AI (Claude Code or Codex), then **Sign in**, then follow the banner to Install-Buddy.

If you'd rather use a Terminal, `bash install.sh` in the Torus-Installer folder is the same installer.

## Reach the Torus from your phone

The Torus listens only on the computer it runs on. To reach it from a phone, put that computer on a [Tailscale](https://tailscale.com) network and open a Funnel to the Torus's remote port; the Torus then serves your phone over a real HTTPS address, and pairs it by QR code.

1. Install Tailscale on the computer that runs the Torus and sign in. On Windows, also choose **Run unattended** in Tailscale's tray menu, so the tunnel survives you signing out, and keep the PC awake.
2. In a terminal (PowerShell on Windows) run `tailscale funnel --bg 8850`. The first time, Tailscale prints a link to switch Funnel on for your network; follow it once. The command prints your Torus's public address, which looks like `https://<name>.<tailnet>.ts.net`.
3. Open the Torus Settings page, scroll to **Remote access**, paste that address and save. Type a name for your phone and press **Pair**, then scan the QR code with the phone's camera and tap **Open Torus**. Add it to your home screen from the share menu if you like.

A Mac also offers a share-sheet Shortcut for saving links; on Windows, paste links into Capture instead.

## Give your Twin an email address

Each Twin can read and send email as himself. Open his page from the Twins table in Settings and scroll to **Email**. He can share the email bridge account, have an account of his own, or none. For his own account, create a Gmail for him, turn on 2-Step Verification, make an app password (the page folds the exact steps), and enter the address and that password. Then list, under **Only respond to emails from these accounts**, the people he may answer, turn on **Poll for mail**, and turn on **Respond automatically** if he should answer without you.

He checks that inbox every three minutes. Mail from a listed person reaches him in his room; with Respond automatically on he replies by email and posts one line in his room saying who wrote, what they asked and what he answered. Mail from anyone else is left unread and never reaches him. One email gets one reply, never a reply to a bounce, an auto-reply or a mailing list; several new mails from one person become one reply. Incoming Twin mail stays in the email conversation; it is not automatically captured into the Library.

## Ask your Twin to do something on a schedule

Tell your Twin what to do and when, in his room, and he sets it up as a scheduled task. At the time you named, the Torus posts your request into his room as a message from you, and he does it the way he does anything you ask, with his memory and all his tools; the result is right there in the room. Enter your own email address on the Human card in Settings if you want him to be able to write to you.

## If Setup can't install your AI

The Setup card's Install button is the easy way. If it fails, or you'd rather do it yourself, install one of these and sign in to it with your own account; the Torus finds it. A Claude Code or Codex you already have works too.

**Claude Code** (needs a paid Claude plan). This is the command-line program, not the Claude Desktop app; Desktop is fine to have, but the Torus cannot use it.

- Windows: open PowerShell and paste `irm https://claude.ai/install.ps1 | iex`
- Mac: open Terminal and paste `curl -fsSL https://claude.ai/install.sh | bash`

On Windows the installer may warn that its folder is not in your PATH, and typing `claude` may then fail in red. **That is fine.** The Torus finds it anyway. To sign in, paste `& "$env:USERPROFILE\.local\bin\claude.exe"`, follow the browser, then type `/exit`.

**Codex** (needs a paid ChatGPT plan). On Windows, the Codex app from the Microsoft Store is enough: install it, sign in, and the Torus uses the Codex inside it (September 2026 build or later; an older Store build refuses to be started by other programs, and updating it fixes that). On a Mac, the ChatGPT app is enough the same way. Or, on either, install the command-line Codex with `npm install -g @openai/codex` and `codex login`; the Torus prefers that copy when both are present. If you have a working Codex somewhere else, give its path on the Setup card.

## Already have the Torus? Upgrade with the same steps

You can upgrade directly from an earlier build; there is no need to install intermediate releases. Use the same computer and user account as before. Do not uninstall the Torus or remove its data folder.

1. Let active Twin turns and other work finish: the upgrade stops the Torus briefly.
2. Download the new package for your computer. On **Windows**, right-click the zip, choose **Extract All**, then open **Torus-Installer** in the extracted folder and run **install.cmd** (shown as **install** if file extensions are hidden). On a **Mac**, unpack the archive for Apple silicon or Intel, then open **Install Torus.command**. Use the unsigned-beta opening steps above if your computer asks.
3. The installer recognises the existing installation and says it will upgrade. You should not need to create another Twin, choose a new data folder, or repeat setup. If it unexpectedly asks for a fresh installation, stop and report that instead of creating a second one.
4. Wait for the completion message: **Torus upgraded from … to …**, followed by the number of files checked before and after. Keep the installer window open until it finishes. Browser and phone connections may drop while the Torus restarts.
5. Reopen your usual Torus bookmark or refresh the page. Your existing Twins, chats and Library should be there. Sign-ins are retained; reconnect only if a provider reports that a sign-in has expired. If an earlier chat message failed, use **Retry** on that message.

The installer checks your content before and after replacement and reports that it has not changed. It refreshes the Twins' tool wiring and Install-Buddy's generated instructions. The previous application is kept until the next upgrade, and the upgrader attempts to restore it if replacement fails. If the installer reports an error, keep the message and ask for help; do not delete your data or start over.

For captures that failed on a Codex-only installation, follow **If captures are waiting for enrichment** below after upgrading. The upgrade adds recovery controls but does not silently overwrite an older saved Claude choice.

## Keeping the AI tools up to date

The Torus checks for Claude Code and Codex updates daily. Open **Settings → Harnesses → Updates** to check now, read the available release information, and choose **Update when idle**. It checks automatically but only installs an update you approve. It shows newly introduced models when the release information identifies them; it does not promise account access to every announced model. After a successful update it refreshes the model list.

Updating Claude Desktop does not necessarily update the Claude Code executable the Torus uses. Updates supplied inside a desktop or editor app may need that app's own updater; the Torus shows the appropriate instructions.

## If captures are waiting for enrichment

Open **Settings → Enrichment**. New automatic choices follow installed harnesses enabled for your Twins. If an older installation saved Claude on a Codex-only computer, choose an available Codex model and a Twin with Codex enabled, then press **Save changes**. Alternatively choose Automatic for both fields. Older saved choices are preserved for you to correct rather than silently changed.

Open **Capture → Prior capture activity**, retry one affected note, and check the result before retrying the rest. The original notes remain intact; do not delete and recapture them. Unavailable harnesses and sign-in failures now hold work with an explanation instead of cancelling each capture.

## Restart as a last resort

**Settings → Status → Restart Torus…** asks for confirmation, restarts the Torus, and reconnects the browser when it returns. A restart interrupts running work, so finish it first when possible. It does not restart Tailscale or repair an offline network connection. If the Torus cannot serve Settings at all, use the operating system's service controls or restart the computer.

## Where things live

- **Your data**, the one folder to back up: the Torus folder you chose. Twins, their memory, your Library notes.
- The application: `%LOCALAPPDATA%\TorusBeta` on Windows, `~/Library/Application Support/TorusBeta` on a Mac.
- To remove it, run **Remove Torus** in the application folder. Your data and your Twins' sign-ins are kept.

## Privacy

Everything stays on your computer. The Torus listens only on 127.0.0.1, your own machine. What your Twin reads and writes goes to the AI provider you signed in to, under your own account and their terms, and nowhere else.
