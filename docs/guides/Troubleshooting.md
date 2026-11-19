# Troubleshooting

This guide covers solutions to the following common problems.

## 1. `brewhy` is not found

Check the command path.

```bash
command -v brewhy
```

If nothing is printed, check the `PATH` line in your shell startup file.

- Installer: `$HOME/.local/bin`
- [Manual Installation](Manual-Installation.md): `$HOME/.brewhy/dist`

## 2. `brewhy` stops working after a rebuild

Each build recreates `dist` and removes the `brewhy` link.

Run this in the clone after every build.

```bash
chmod +x dist/cli.js && ln -s cli.js dist/brewhy
```

## 3. The installer rejects your Node.js version

The installer needs `Node.js 22.22.2+ (22.x)` or `24.15+`.

Check your version.

```bash
node --version
```

Update Node.js, then run the installation command again.
