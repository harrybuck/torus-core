# The Torus

A home for your personal AI Twin: a small program that runs on your own computer, keeps your Twin's memory in one folder you own, and opens in your browser. Your Twin works through an AI subscription you already have, Claude or ChatGPT; the Torus adds no cloud service of its own.

This is a **private beta**. Expect rough edges, and tell us what you hit.

## Download (build 3c13c94)

| Your computer | File |
|---|---|
| Windows 10 or 11 | [torus-win-x64-3c13c94.zip](https://github.com/harrybuck/torus-core/releases/download/beta-3c13c94/torus-win-x64-3c13c94.zip) |
| Mac with Apple silicon (M1 or later) | [torus-mac-arm64-3c13c94.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-3c13c94/torus-mac-arm64-3c13c94.tar.gz) |
| Mac with an Intel processor | [torus-mac-x64-3c13c94.tar.gz](https://github.com/harrybuck/torus-core/releases/download/beta-3c13c94/torus-mac-x64-3c13c94.tar.gz) |

Checksums: [Mac](https://github.com/harrybuck/torus-core/releases/download/beta-3c13c94/SHA256SUMS-3c13c94.txt) · [Windows](https://github.com/harrybuck/torus-core/releases/download/beta-3c13c94/SHA256SUMS-win-3c13c94.txt)

## Before you install: your Twin needs an AI to think with

Install **one** of these first, and sign in to it with your own account.

**Claude Code** (needs a paid Claude plan). This is the command-line program, not the Claude Desktop app; Desktop is fine to have, but the Torus cannot use it.

- Windows: open PowerShell and paste `irm https://claude.ai/install.ps1 | iex`
- Mac: open Terminal and paste `curl -fsSL https://claude.ai/install.sh | bash`

On Windows the installer may warn that its folder is not in your PATH, and typing `claude` may then fail in red. **That is fine.** The Torus finds it anyway. To sign in, paste `& "$env:USERPROFILE\.local\bin\claude.exe"`, follow the browser, then type `/exit`.

**Codex** (needs a paid ChatGPT plan): `npm install -g @openai/codex`, then `codex login`. On Windows use this npm version; the Codex inside the ChatGPT Store app cannot be started by other programs.

## Install on Windows

1. Download the zip. Right-click it and choose **Extract All**. Do not run anything from inside the zip.
2. Open the extracted folder and double-click **install**.
3. Windows may show a blue *Windows protected your PC* box, because this beta is not yet code-signed. Choose **More info**, then **Run anyway**.
4. Answer the two questions: your name, and where your data should live (press Enter for a Torus folder in your user folder).
5. Settings opens in your browser. Follow the banner to **Install-Buddy**, who confirms everything works and helps you create your own Twin.

No administrator rights are needed. The Torus starts by itself when you sign in to Windows, and a **Torus** shortcut appears on your Desktop.

**If Windows refuses with no Run anyway button**, your PC has Smart App Control switched on, which is common on new Windows 11 computers. Open PowerShell and unblock the extracted folder, then double-click **install** again (type the folder name as it appears in your Downloads):

```
gci ~\Downloads\torus-win-x64-3c13c94 -r | Unblock-File
```

**A plain empty window appears while the Torus runs. Leave it open** (minimise it). On this beta that window is the Torus; closing it stops your Twins. If it does get closed, `schtasks /run /tn "Torus Serve"` in PowerShell brings the Torus back.

## Install on a Mac

1. Download the archive for your Mac and double-click it to unpack.
2. Open Terminal, type `bash ` (with the space), drag **install.sh** from the unpacked folder into the Terminal window, and press Return.
3. Answer the two questions. Settings opens in your browser; follow the banner to Install-Buddy.

## Already have the Torus? Upgrade with the same steps

Download the new build and install it exactly as above. The installer sees your existing Torus, says it will upgrade, and replaces only the application. Your data folder, your Twins, their memory and their sign-ins are not touched: every one of your files is fingerprinted before and after, and the installer tells you how many it checked and that none changed. If anything about your data did change, the upgrade stops and puts the previous application back. The previous application is kept beside the new one until the next upgrade.

After upgrading, open your Twin's room. If a message had failed before the upgrade, press **Retry** on it.

## Where things live

- **Your data**, the one folder to back up: the Torus folder you chose. Twins, their memory, your Library notes.
- The application: `%LOCALAPPDATA%\TorusBeta` on Windows, `~/Library/Application Support/TorusBeta` on a Mac.
- To remove it, run **Remove Torus** in the application folder. Your data and your Twins' sign-ins are kept.

## Privacy

Everything stays on your computer. The Torus listens only on 127.0.0.1, your own machine. What your Twin reads and writes goes to the AI provider you signed in to, under your own account and their terms, and nowhere else.
