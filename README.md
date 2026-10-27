# Wispkin

**English** · [Español](README.es.md)

**Your AI assistant, with a face, right on your desktop.**

Wispkin is a Windows app that puts your AI assistant on your desktop. **Chispa**, a tiny blue will-o'-the-wisp, floats over your windows and reacts to what the AI is doing: thinking, working, asking for permission, finishing. Click it to open a chat bubble.

- **Works with Claude** using your own Anthropic API key. The assistant can read and edit files and run commands on your computer, **always asking your permission first**. You pay only for your own usage, directly to Anthropic, and Wispkin shows how much you've spent today, with an optional daily cap.
- **Works with Ollama**: models that run on your PC, free, and your conversation never leaves your machine. In this version, Ollama is chat only.
- **Chispa grows with you**: energy, mood, levels and unlockable variants. It never gets sick, never guilt-trips you for not using it, and you can turn it off.
- **Opens the same conversation in Claude Code**, and imports **Codex Pets** and **Shimeji** avatars.
- **Private**: no accounts, no telemetry, no ads.

> 🧪 **Beta.** Wispkin is in beta and may have bugs. When you ask it to work with files, use a test folder or a project you have backed up.
>
> 🌐 **The app's interface is in Spanish for now.** English is coming.

![Chispa on the desktop with its chat bubble open: it's asked to help organize the Downloads folder and explains how it would do it](captura.png)

## Download

Download the `Wispkin-Setup-<version>.exe` installer from **[Releases](../../releases/latest)**. Wispkin updates itself when a new version is available.

Coming soon to the Microsoft Store.

### Windows SmartScreen warning

The installer isn't signed with a paid certificate yet, so Windows may show **"Windows protected your PC"**. To continue, click **More info → Run anyway**.

If you'd like to verify the file, compare its SHA-256 hash with the one in the release notes:

```powershell
Get-FileHash .\Wispkin-Setup-<version>.exe
```

## Requirements

- Windows 10 (1809 or later) or 11, 64-bit.
- **For Claude:** an Anthropic account with an API key (paid, usage-based). We recommend a key used only for Wispkin, with a spending limit.
- **For Ollama:** [Ollama](https://ollama.com/download) installed and a model downloaded (for example `ollama pull llama3.2`). Useful models need a GPU with 6–8 GB of VRAM or more. Without a GPU it works, but slowly.
- **Optional:** Claude Code, for "Open in Claude Code".

## Getting started

1. Install and open Wispkin. Chispa appears on your desktop and an icon appears in the system tray.
2. Click Chispa and choose its brain: **Claude** (paste your key) or **Ollama** (pick a model).
3. Write to it. Whenever it wants to touch something on your computer, it asks your permission first.

Shortcut: **Ctrl+Alt+P** opens and closes the chat bubble. The tray menu has *Do not disturb*, avatar switching and *Import avatar…*.

## Privacy and terms

- Everything is stored on your computer (`%APPDATA%\wispkin`). Your keys are encrypted with Windows encryption.
- Your conversations go directly from your computer to the provider you chose, using your key. Wispkin has no servers that receive them.
- No telemetry or analytics. To check for updates, the app queries this GitHub repository.

Read the [privacy policy](PRIVACIDAD.md) and the [terms of use](TERMINOS.md) (currently in Spanish).

## Report a bug or share feedback

- **Bugs:** open an [issue](../../issues/new) using the template. Issues are public, so **never paste your API key** or private information.
- **Feedback:** [feedback form](https://forms.gle/bBhzJXpousYvmrnL9) (2 minutes).
- **Security** (for example, something that exposes your key or an action taken without permission): don't open a public issue. Email wispkin.app@gmail.com instead.

## About this repository

This repository only hosts Wispkin's installers, release notes and update channel. The source code is not public for now.

---

Wispkin is an independent project. **It is not affiliated with, sponsored by or endorsed by Anthropic, OpenAI, Ollama or Microsoft.** Claude is a trademark of Anthropic, Codex of OpenAI, and Ollama of its respective owners. They are mentioned only to indicate compatibility.

© 2026 Wisplight Studio
