# Installing ARB for Codex

Enable ARB skills in Codex via native skill discovery.

## Prerequisites

- Git

## Installation

1. Clone this repository:

   ```bash
   git clone <YOUR_ARB_REPO_URL> ~/.codex/arb
   ```

2. Create the skills symlink:

   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.codex/arb/skills ~/.agents/skills/arb
   ```

   Windows (PowerShell):

   ```powershell
   New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
   cmd /c mklink /J "$env:USERPROFILE\.agents\skills\arb" "$env:USERPROFILE\.codex\arb\skills"
   ```

3. Restart Codex (quit and relaunch the CLI) to discover the skills.

## Verify

```bash
ls -la ~/.agents/skills/arb
```

You should see a symlink (or junction on Windows) pointing to your ARB skills directory.

## Updating

```bash
cd ~/.codex/arb && git pull
```

## Uninstalling

```bash
rm ~/.agents/skills/arb
```

Optionally delete the clone:

```bash
rm -rf ~/.codex/arb
```
