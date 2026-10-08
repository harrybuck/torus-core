# The Torus

A home for your personal AI Twin: a small program that runs on your own computer, keeps your Twin's memory in one folder you own, and opens in your browser. Your Twin works through an AI subscription you already have, Claude or ChatGPT; the Torus adds no cloud service of its own.

This is a **private beta**. Expect rough edges, and tell us what you hit.

## Download (build ba9f95a)

| Your computer | File |
|---|---|
| Windows 10 or 11 | [torus-win-x64-ba9f95a.zip](https://github.com/harrybuck/torus-core/releases/download/beta-ba9f95a/torus-win-x64-ba9f95a.zip) |
| Mac with Apple silicon (M1 or later) | [torus-mac-arm64-ba9f95a.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-ba9f95a/torus-mac-arm64-ba9f95a.tar.gz) |
| Mac with an Intel processor | [torus-mac-x64-ba9f95a.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-ba9f95a/torus-mac-x64-ba9f95a.tar.gz) |

Checksums: [Mac](https://github.com/harrybuck/torus-core/releases/download/beta-ba9f95a/SHA256SUMS-ba9f95a.txt) · [Windows](https://github.com/harrybuck/torus-core/releases/download/beta-ba9f95a/SHA256SUMS-win-ba9f95a.txt)

[What changed since build 3484a77](https://github.com/harrybuck/torus-core/releases/tag/beta-ba9f95a) · [Recovery steps for failed enrichment](#if-captures-are-waiting-for-enrichment)

## Before you install: your Twin needs an AI to think with

Install **one** of these first, and sign in to it with your own account.

**Claude Code** (needs a paid Claude plan). This is the command-line program, not the Claude Desktop app; Desktop is fine to have, but the Torus cannot use it.

- Windows: the Torus can install it for you from the Setup card (Install Claude Code). Or open PowerShell and paste `irm https://claude.ai/install.ps1 | iex`
- Mac: open Terminal and paste `curl -fsSL https://claude.ai/install.sh | bash`

On Windows the installer may warn that its folder is not in your PATH, and typing `claude` may then fail in red. **That is fine.** The Torus finds it anyway. To sign in, paste `& "$env:USERPROFILE\.local\bin\claude.exe"`, follow the browser, then type `/exit`.

**Codex** (needs a paid ChatGPT plan). On Windows, the Codex app from the Microsoft Store is enough: install it, sign in, and the Torus uses the Codex inside it (September 2026 build or later; an older Store build refuses to be started by other programs, and updating it fixes that). On a Mac, the ChatGPT app is enough the same way. Or, on either, install the command-line Codex with `npm install -g @openai/codex` and `codex login`; the Torus prefers that copy when both are present. If you have a working Codex somewhere else, give its path on the Setup card.

## Install on Windows

1. Download the zip. Right-click it and choose **Extract All**. Do not run anything from inside the zip.
2. Open the extracted folder and double-click **install**.
3. Windows may show a blue *Windows protected your PC* box, because this beta is not yet code-signed. Choose **More info**, then **Run anyway**.
4. Answer the two questions: your name, and where your data should live (press Enter for a Torus folder in your user folder).
5. Settings opens in your browser. Follow the banner to **Install-Buddy**, who confirms everything works and helps you create your own Twin.

**Moving from the Obsidian-era Torus?** Tell Install-Buddy. He finds your old vault, tells you what he found, and on your go brings the old conversations into your new Twin's memory and every note and idea into the Library. Nothing in the old vault is changed or deleted.

No administrator rights are needed. The Torus starts by itself when you sign in to Windows, and a **Torus** shortcut appears on your Desktop.

**If Windows refuses with no Run anyway button**, your PC has Smart App Control switched on, which is common on new Windows 11 computers. Open PowerShell and unblock the extracted folder, then double-click **install** again (type the folder name as it appears in your Downloads):

```
gci ~\Downloads\torus-win-x64-ba9f95a -r | Unblock-File
```

**No window while the Torus runs.** The Torus and its memory jobs run with no window on any account. If the Torus ever stops, the half-hourly memory job starts it again; `schtasks /run /tn "Torus Serve"` in PowerShell starts it at once.

## Install on a Mac

1. Download the archive for your Mac and double-click it to unpack.
2. Open the unpacked folder and double-click **Install Torus.command**. It opens a Terminal window and runs the installer there.
3. If macOS says it can't be opened because the developer is unidentified (this beta is not yet signed), right-click **Install Torus.command**, choose **Open**, then **Open** again.
4. Answer the two questions. Settings opens in your browser; follow the banner to Install-Buddy.

If you'd rather use a Terminal, `bash install.sh` in the unpacked folder is the same installer.

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

## Already have the Torus? Upgrade with the same steps

Download the new build and install it exactly as above. The installer sees your existing Torus, says it will upgrade, and replaces only the application. Your data folder, your Twins, their memory and their sign-ins are not touched: every one of your files is fingerprinted before and after, and the installer tells you how many it checked and that none changed. If anything about your data did change, the upgrade stops and puts the previous application back. The previous application is kept beside the new one until the next upgrade.

After upgrading, open your Twin's room. If a message had failed before the upgrade, press **Retry** on it.

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
