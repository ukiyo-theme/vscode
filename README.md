# Ukiyo for VS Code

Ukiyo is a color theme for VS Code, VSCodium, Cursor and other VS Code-based editors.

[View the palette](https://ukiyo-theme.github.io/palette/)

## Variants

| Theme label | Appearance | Background | Description |
|---|---|---|---|
| Ukiyo Umi | Dark | `#1A1A22` | Sea variant with a cool background. |
| Ukiyo Yoru | Dark | `#161514` | Night variant with a darker, warmer background. |
| Ukiyo Kami | Light | `#D2CCBC` | Paper variant at about 60% brightness. |

![Ukiyo Umi palette preview](images/umi.png)

![Ukiyo Yoru palette preview](images/yoru.png)

![Ukiyo Kami palette preview](images/kami.png)

Every text color meets a minimum WCAG contrast against the editor background. Comments are at least 4.5:1 and syntax colors at least 5:1.

## How to use

### Install the VSIX

Download the [Ukiyo VSIX](https://ukiyo-theme.github.io/palette/downloads/ukiyo.vsix). In VS Code, Cursor, or VSCodium, run **Extensions: Install from VSIX…** from the Command Palette and choose the downloaded file.

### Build from source

To build the package locally, clone the repository and run these commands.

```sh
git clone https://github.com/ukiyo-theme/vscode ukiyo-vscode
cd ukiyo-vscode
npx @vscode/vsce package
```

Install the generated file from the Command Palette or from the terminal.

```sh
code --install-extension ukiyo-*.vsix
```

You can also copy or symlink the cloned folder into `~/.vscode/extensions` and restart VS Code. Cursor and VSCodium use their own extensions folders and CLI commands.

### Select a theme

Run **Preferences: Color Theme** from the Command Palette and choose **Ukiyo Umi**, **Ukiyo Yoru**, or **Ukiyo Kami**.

### Follow the system color scheme

Add these settings to your user `settings.json` to use Ukiyo Umi in dark mode and Ukiyo Kami in light mode. Use `"Ukiyo Yoru"` as the preferred dark theme if you prefer its warmer background.

```json
{
  "window.autoDetectColorScheme": true,
  "workbench.preferredDarkColorTheme": "Ukiyo Umi",
  "workbench.preferredLightColorTheme": "Ukiyo Kami"
}
```

### Customize colors

Use `workbench.colorCustomizations` for interface colors and `editor.tokenColorCustomizations` for syntax colors. In each setting, put the exact theme label in square brackets to apply the overrides only to that theme.

```json
{
  "workbench.colorCustomizations": {
    "[Ukiyo Umi]": {
      "sideBar.background": "#20202A"
    }
  },
  "editor.tokenColorCustomizations": {
    "[Ukiyo Umi]": {
      "comments": "#9297A8"
    }
  }
}
```

## Regenerate the theme files

The files in `themes/` are generated from `palette.json` in [ukiyo-theme/palette](https://github.com/ukiyo-theme/palette). Make shared color changes in the palette and regenerate the files. With both repositories cloned side by side as `vscode` and `palette`, run this command from the VS Code repository.

```sh
python3 ../palette/scripts/build.py vscode --out .
```

## License

MIT
