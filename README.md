<p align="center">
  <img src="https://raw.githubusercontent.com/norrathreborn/CrusadersModuleManager/main/Assets/Images/crusadersmodulemanagerlogo.png" alt="Crusaders Module Manager Logo" width="650">
</p>

<h1 align="center">Crusaders Module Manager V0.0.6</h1>

<p align="center">
  <strong>AzerothCore Module Management Tool</strong>
</p>

<p align="center">
  A safer, cleaner desktop utility for discovering, installing, backing up, removing, and updating AzerothCore modules without manually juggling GitHub links, module folders, and backup copies.
</p>

---

## About

**Crusaders Module Manager** is a desktop GUI tool built to make AzerothCore module management easier and safer.

Instead of manually browsing GitHub, cloning module repositories, copying folders, backing up old modules, or trying to remember which modules are installed, this tool gives you a single interface for managing modules inside your AzerothCore fork.

It is designed for:

- AzerothCore repack builders
- Private server developers
- Module testers
- People maintaining custom AzerothCore forks
- Users who want safer install, backup, remove, and update workflows

The tool does **not** build AzerothCore for you, edit your database, run SQL automatically, or execute module scripts. It focuses on safely managing the module folders and leaving final review/build steps under user control.

---

## Downloads

### Windows

Download:

`CrusadersModuleManager_Windows_Setup_V006.zip`

Extract the ZIP, then run:

`CrusadersModuleManager_Setup_V006.exe`

The Windows installer has been tested and confirmed working.

### Linux

Download:

`CrusadersModuleManager_Linux_Source_V006.zip`

Linux support is currently **source-only** through:

`Crusaders_Module_Manager_V006.pyw`

A packaged Linux executable or Linux installer is not included yet. Linux packaging will need to be handled as a separate future build target.

---

## What It Can Do

- Discover official AzerothCore `mod-*` repositories from GitHub
- Discover community catalogue modules using the `azerothcore-module` topic
- Add custom GitHub module URLs manually
- Detect local-only modules already inside your AzerothCore `modules` folder
- Search and sort the module table
- Click safe GitHub URLs directly from the table
- Save and load module lists
- Install selected modules with `git clone`
- Backup selected installed modules
- Remove selected modules safely by moving them to backup
- Update selected installed Git repositories using `git pull --ff-only`
- Skip dirty or locally changed repositories during update
- Show a Security Notice explaining third-party module risks
- Keep installed modules unchecked by default for safer workflows

---

## Safety First

Crusaders Module Manager is intentionally conservative.

Checkboxes do **not** mean installed state.  
Checkboxes mean:

> Perform the selected action on this module right now.

Unchecked modules are never touched.

The tool does **not** auto-run:

- SQL files
- Scripts
- Executables
- BAT files
- PowerShell files
- Python files
- Shell files
- Module files

For update operations, the tool only uses:

`git pull --ff-only`

It does **not** use:

- `git reset`
- `git stash`
- `git pull --force`
- forced merges
- destructive delete operations

Remove operations move modules to backup instead of permanently deleting them.

---

## Backup Behavior

The tool creates backups for important actions.

Backup examples:

```text
Backups\Selected_Modules
Backups\Removed_Modules
Backups\Before_Update
