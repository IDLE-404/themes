# Contributing a Theme

Anyone can submit a theme to the Tema marketplace. Here's how.

## Theme structure

Each theme lives in its own folder:

```
your-theme-name/
  theme.json      ← required
  preview.png     ← required  (recommended: 400×250 px)
  wallpaper.png   ← optional  (will be applied as desktop background)
  icons/          ← optional  (folder icon .ico files)
    folder.ico
```

## theme.json format

```json
{
  "id": "your-theme-name",
  "name": "Your Theme Name",
  "version": "1.0.0",
  "author": "your-github-username",
  "description": "One sentence about your theme.",
  "preview": "preview.png",
  "wallpaper": "wallpaper.png",
  "accentColor": "#your-hex-color",
  "folderIcons": {
    "enabled": false,
    "iconPath": "icons/folder.ico"
  },
  "colors": {
    "accent":     "#hex",
    "background": "#hex",
    "surface":    "#hex",
    "text":       "#hex"
  },
  "animations": {
    "windowOpen":     "spring",
    "windowClose":    "fade",
    "minimize":       "spring",
    "taskbarHover":   "glow",
    "menuTransition": "fade",
    "tooltipFade":    true
  },
  "widgets": [],
  "tags": ["dark", "minimal"],
  "createdAt": "2026-01-01"
}
```

### Valid animation values
- `windowOpen` / `windowClose` / `minimize`: `"spring"` | `"fade"` | `"slide"` | `"none"`
- `taskbarHover`: `"glow"` | `"scale"` | `"none"`
- `menuTransition`: `"fade"` | `"slide"` | `"none"`

### Suggested tags
`dark` `light` `minimal` `colorful` `purple` `blue` `pink` `green` `warm` `cool`
`space` `nature` `hacker` `clean` `gradient`

## Submitting

1. Fork this repository
2. Add your theme folder with `theme.json` and `preview.png`
3. Add your theme entry to `index.json` (keep alphabetical order by `id`)
4. Open a Pull Request

Your theme will appear in the Tema marketplace after the PR is merged.

## Rules

- No offensive or harmful content
- `accentColor` must be a valid 6-digit hex color
- `preview.png` is required — no blank previews
- `id` must be lowercase, hyphens only (e.g. `my-cool-theme`)
- `version` follows semver (e.g. `1.0.0`)
