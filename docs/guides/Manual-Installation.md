# Manual Installation

This guide covers manual installation, updates and removal.

## 1. Requirements

- `macOS` with `Homebrew` — [requirements](https://docs.brew.sh/Installation#macos-requirements).
- `Node.js 22.22.2+ (22.x)` or `24.15+`, with `npm`.
- `Git` for building from source.

Install `Git` with `xcode-select --install` if it is missing.

### 1.1. Compatibility

- The build and automated checks passed with `Node.js 22.23.5` on `macOS 27.2.1` (`Apple Silicon`).

## 2. Install

Open a new terminal and follow these steps.

```bash
git clone https://github.com/wereallcode/brewhy.git "$HOME/.brewhy"
```

```bash
cd "$HOME/.brewhy" && npm ci --include=dev && npm run build
```

```bash
chmod +x dist/cli.js && ln -s cli.js dist/brewhy
```

Run `brewhy` with this command.

```bash
./dist/brewhy
```

### 2.1. Add to `PATH`

Follow these steps to add `brewhy` to your `PATH` and run it from any directory.

```zsh
vi ~/.zshrc
```

Add this line at the end of the file and save it.

```zsh
export PATH="$HOME/.brewhy/dist:$PATH"
```

Apply the change.

```zsh
source ~/.zshrc
```

Run `brewhy`. 🥳

```zsh
brewhy
```

## 3. Update

Follow these steps to update your local copy and rebuild.

```bash
cd "$HOME/.brewhy" && git pull --ff-only
```

```bash
npm ci --include=dev && npm run build
```

```bash
chmod +x dist/cli.js && ln -s cli.js dist/brewhy
```

## 4. Uninstall

1. Remove the `PATH` line from your shell startup file.
2. Open a new terminal.
3. Delete `$HOME/.brewhy` if you no longer need the source.
