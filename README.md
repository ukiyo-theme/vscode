# Ukiyo for VS Code

The [Ukiyo](https://github.com/ukiyo-theme/palette) color theme for VS Code, VSCodium, Cursor and other VS Code-based editors.

| Theme | Appearance | Background |
|---|---|---|
| Ukiyo Umi | dark | `#1A1A22` |
| Ukiyo Yoru | darker, muted | `#161514` |
| Ukiyo Kami | light, about 60% brightness | `#D2CCBC` |

Every text color meets a minimum WCAG contrast against the editor background. Comments are at least 4.5:1 and syntax colors at least 5:1.

## Install

The extension isn't on the Marketplace or Open VSX yet. To install it from source:

```sh
git clone https://github.com/ukiyo-theme/vscode ukiyo-vscode
cd ukiyo-vscode
npx @vscode/vsce package
code --install-extension ukiyo-0.1.0.vsix
```

Then run **Preferences: Color Theme** and pick a Ukiyo theme.

## Changing the colors

Don't edit `themes/*.json` by hand. They are generated from `palette.json` in [ukiyo-theme/palette](https://github.com/ukiyo-theme/palette):

```sh
python3 ../palette/scripts/build.py vscode --out .
```

The path assumes both repos are cloned side by side.

## License

MIT
