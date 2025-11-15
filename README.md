# WorkSpaceWrapper

WorkSpaceWrapper is the stable entry point for using the [CodingBooth WorkSpace](https://github.com/NawaMan/WorkSpace).

It does not contain WorkSpace itself — instead, it reliably downloads, verifies, and launches the real workspace.sh tool inside your project.

# Quick Install (per project)

Run the following on the project base folder.

```shell
curl -fsSL -o workspace \
  https://github.com/NawaMan/WorkSpaceWrapper/releases/latest/download/workspace \
  && chmod +x workspace
```

# Why the Wrapper Exists

The actual workspace.sh (from the WorkSpace project) evolves quickly.
Your workflow shouldn’t break when the tool changes — and you shouldn’t have to manually fetch updates.

The Wrapper solves this by being:

## ✔ Stable

This script rarely changes. It stays safe and dependable while the real WorkSpace tool updates independently.

## ✔ Self-contained

It does not auto-update itself and does not depend on the WorkSpace repo.
You can check it into any project and know it will behave the same.

## ✔ Responsible for verification

Before running WorkSpace, it ensures:
- The tool exists locally
- The SHA1 checksum matches
- The tool is newer than its checksum
- The correct version is downloaded when requested

If anything is missing or corrupted, the Wrapper tells you to run:

```shell
workspace update
```

## ✔ A single cross-platform entry point

The repository includes:

- `workspace` — the Bash wrapper

# Quick Start

Add the wrapper to your repository (or install it globally).

In your terminal, run:

```shell
./workspace install
```

This downloads and verifies the real WorkSpace tool into:

```shell
.workspace/tools/workspace.sh

```

After that, just use:

```shell
./workspace <command>
```

All commands are forwarded to the actual WorkSpace once integrity checks pass.

Full Usage

Run:

```shell
./workspace help
```

to see all supported commands and options.