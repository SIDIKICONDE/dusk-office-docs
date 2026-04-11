# Dusk Office — Extended guide

Dark themes for **Visual Studio Code** and **Cursor**.

**This repository** ([dusk-office-docs](https://github.com/SIDIKICONDE/dusk-office-docs)) is the public documentation. **Main readme** (install, switch theme, quick settings): **[README.md](./README.md)**. **Extension source code:** [SIDIKICONDE/dusk-office](https://github.com/SIDIKICONDE/dusk-office).

**Open VSX:** [dekidev.dusk-office](https://open-vsx.org/extension/dekidev/dusk-office)

<span style="color:#4ec9b0">◆</span> <span style="color:#569cd6">Dream</span> <span style="color:#c586c0">in</span> <span style="color:#ce9178">color</span> <span style="color:#dcdcaa">◆</span>

## Overview

`Dusk Office` is a theme pack with clean contrast and readable syntax.

It includes dark, light, warm, and high-contrast variants for daily use.

**Note:** This extension installs **Material Icon Theme** (Explorer icons) and [**Markdown All in One**](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) (Markdown shortcuts, snippets, TOC, list tools) via `extensionPack` — both ship with Dusk Office. Uninstall either extension if you do not want it. Theme **colors** for the Markdown preview (`textLink`, `markdownAlert`, etc.) come from Dusk Office's color themes.

**macOS — title bar:** the **system menu bar** (Apple menu) always follows macOS appearance. The **window** title bar is switched to **custom** when a Dusk Office theme is active so it matches `titleBar.*` in the theme (native title bars often stay dark with a light editor theme). Turn off with setting **`duskOffice.titleBar.alignWithTheme`**: `false`, or set **`window.titleBarStyle`**: `native` yourself if you prefer the native bar.

## Highlights

- <span style="color:#4ec9b0">Dark themes</span> for daily work
- **Complete UI theming** — title bar, sidebar, panel, tabs, notifications, status bar, activity bar
- **Markdown preview** — `textLink`, block quotes, fenced code (`textCodeBlock` / `textPreformat`), and GFM **markdownAlert** (note / tip / important / warning / caution) aligned with each variant's palette; **Markdown All in One** (bundled via `extensionPack`) adds shortcuts, snippets, and list/table helpers for `.md` files
- **Advanced semantic tokens** — const/let/var differentiation, async functions, decorators, type parameters
- **Full Git integration** — gutter decorations, file status colors, diff editor, merge conflicts
- **Complete terminal palette** — ANSI 16 colors with cursor styling
- **Editor enhancements** — line highlight, selection, search matches, word highlight, indent guides
- **Workspace trust indicators** — untrusted content warnings, extension icons
- Control Center for quick theme actions
- Auto switch by hour
- Favorite theme on startup
- Per-workspace theme memory
- Status bar switcher
- Semantic highlighting and TextMate token styling
- Variants for dark, light, warm, and high-contrast setups
- Good editor defaults

## Included Themes

| Theme | Style |
|------|------|
| <span style="color:#4ec9b0">**Dusk Office**</span> | Core dark theme with cyan and pink accents. |
| <span style="color:#569cd6">**Dusk Office Abyss**</span> | Deep blue night palette with vivid cyan highlights. |
| <span style="color:#ce9178">**Dusk Office Dawn**</span> | Brighter dark surfaces with bold syntax contrast. |
| <span style="color:#6a9955">**Dusk Office Bay**</span> | Lagoon-inspired green tones and fresh chrome. |
| <span style="color:#808080">**Dusk Office Mist**</span> | Slate blue-gray palette with balanced contrast. |
| <span style="color:#9cdcfe">**Dusk Office Ash**</span> | Neutral gray theme with a clean console feel. |
| <span style="color:#d4d4d4">**Dusk Office Midnight**</span> | Very dark variant, ideal for OLED-style setups. |
| <span style="color:#c586c0">**Dusk Office Nebula**</span> | Purple and mauve accents with a richer atmosphere. |
| <span style="color:#00ffff">**Dusk Office Reef**</span> | Bright cyan neon energy and stronger borders. |
| <span style="color:#dcdcaa">**Dusk Office Nocturne**</span> | Warm vintage terminal aesthetic with amber and copper accents. |
| <span style="color:#ffd700">**Dusk Office Finance**</span> | Premium banking aesthetic with gold, deep green and navy accents. |
| <span style="color:#8b2942">**Dusk Office Corporate**</span> | Sophisticated burgundy-wine theme with refined gold touches. |
| <span style="color:#5c6773">**Dusk Office Light**</span> | Cool, neutral light theme for daytime work. **Built** from Dusk Office Abyss (`npm run build:light`) — mechanical light remap + UI overrides; see `MAINTENANCE.md` → *Dusk Office Light*. |
| <span style="color:#b58900">**Dusk Office Ivory**</span> | Warm paper-like light theme with copper accents. |
| <span style="color:#d4b483">**Dusk Office Dark Ivory**</span> | Warm dark companion to Ivory with cream text. |
| <span style="color:#ffffff;background:#000000;padding:2px 4px;border-radius:3px">**Dusk Office High Contrast**</span> | Stronger separation and clearer focus states. |

### High Contrast — contrast targets

**Dusk Office High Contrast** is tuned for **WCAG 2.1**-style contrast on critical UI pairs (normal text **≥ 4.5:1** AA; where possible **≥ 7:1** AAA for primary reading and selection):

| Pair | Target |
|------|--------|
| Default editor text / background | `#ffffff` on `#000000` (ratio **≥ 21:1**) |
| Selection text / selection fill | `#ffffff` on `#264f78` (aim **≥ 7:1** — AAA for body-sized text) |
| Focus rings (`focusBorder`, list focus) | **Yellow** (`#ffff00`) or **cyan** on black for keyboard / focus visibility |
| Inline chat & inline edit panels | **Yellow** widget border on black; **white** input border; **yellow** focus border on the input |

The theme still **`include`s** Dusk Office Abyss for syntax; non-overridden chrome may show Abyss tints. Adjust with `workbench.colorCustomizations` if your environment needs stricter uniformity.

## Installation

See **[README — Install](./README.md#install)** (Marketplace and VSIX).

## Usage

Enable a theme and daily workflow: **[README — Switch Theme](./README.md#switch-theme)**.

The extension also ships editor-friendly defaults (semantic highlighting, minimap, guides, sticky scroll); user and workspace settings can override them.

### Control Center

Open the Command Palette and run `Dusk Office: Control Center`, or use the status bar entry when enabled, to:

- switch theme variants
- go back to the previous theme
- save and restore a favorite theme
- toggle auto switch
- check the saved workspace theme
- toggle activity bar position
- toggle **Dusk Office · Product** icons (same as command below)
- open settings

### Command IDs

Registered in `package.json` → `contributes.commands`. Use these IDs in `keybindings.json`, tasks, or automation.

| Command ID | Palette title |
|------------|----------------|
| `duskOffice.openControlCenter` | Dusk Office: Control Center |
| `duskOffice.switchThemeVariant` | Dusk Office: Choose Theme |
| `duskOffice.switchToPreviousTheme` | Dusk Office: Previous Theme |
| `duskOffice.setFavoriteTheme` | Dusk Office: Set Favorite |
| `duskOffice.switchToFavoriteTheme` | Dusk Office: Favorite Theme |
| `duskOffice.toggleActivityBarLocation` | Dusk Office: Toggle Activity Bar Position |
| `duskOffice.toggleProductIconTheme` | Dusk Office: Toggle Product Icon Theme |
| `duskOffice.toggleAutoSwitch` | Dusk Office: Toggle Auto Switch |
| `duskOffice.openSettings` | Dusk Office: Settings |

### Settings

Defined in `package.json` → `contributes.configuration` (`duskOffice.*`).

| Key | Default | Description |
|-----|---------|-------------|
| `duskOffice.applyFavoriteOnStartup` | `false` | Apply the favorite theme on startup. |
| `duskOffice.rememberWorkspaceTheme` | `true` | Remember the last Dusk Office theme for each workspace. |
| `duskOffice.statusBar.enabled` | `true` | Show the Dusk Office status bar button. |
| `duskOffice.titleBar.alignWithTheme` | `true` | When a Dusk Office color theme is active, set `window.titleBarStyle` to `custom` so the title bar follows the theme (helps a light editor avoid a stuck-dark native bar on macOS). When you leave Dusk themes or disable this, the previous global title bar style is restored. Does not override if you set `window.titleBarStyle` to `native` yourself in User or Workspace settings. |
| `duskOffice.autoSwitch.enabled` | `false` | Switch between light and dark Dusk Office themes by hour. |
| `duskOffice.autoSwitch.lightTheme` | `Dusk Office Light` | Theme during light hours (enum matches Dusk variants in settings UI). |
| `duskOffice.autoSwitch.darkTheme` | `Dusk Office Midnight` | Theme during dark hours (same enum). |
| `duskOffice.autoSwitch.lightHour` | `7` | Hour (0–23) to start the light theme. |
| `duskOffice.autoSwitch.darkHour` | `18` | Hour (0–23) to start the dark theme. |

### Editor defaults bundled with the extension

`package.json` → `contributes.configurationDefaults` applies these when the extension is enabled (user/workspace settings still win):

- `editor.minimap.enabled` → `true`; `editor.minimap.showSlider` → `always`
- `editor.semanticHighlighting.enabled` → `true`
- `editor.bracketPairColorization.enabled` → `true`
- `editor.guides.bracketPairs` → `active`; `editor.guides.bracketPairsHorizontal` → `active`; `editor.guides.highlightActiveIndentation` → `true`
- `editor.stickyScroll.enabled` → `true`
- `editor.renderLineHighlight` → `line`; `editor.selectionHighlight` → `true`; `editor.linkedEditing` → `true`
- `workbench.tree.renderIndentGuides` → `always`; `workbench.tree.indent` → `14`
- `explorer.decorations.badges` / `explorer.decorations.colors` → `true`

### Source of truth (repo)

| What | Where |
|------|--------|
| Color theme list & JSON paths | [`package.json`](https://github.com/SIDIKICONDE/dusk-office/blob/main/package.json) → `contributes.themes` (17 themes) |
| Product icon theme | [`package.json`](https://github.com/SIDIKICONDE/dusk-office/blob/main/package.json) → `contributes.productIconThemes` (`dusk-office-product` → **Dusk Office · Product**) |
| Theme names for picker, favorite, auto-switch | [`extension.js`](https://github.com/SIDIKICONDE/dusk-office/blob/main/extension.js) → `THEME_VARIANTS` (keep in sync with `package.json` labels) |
| Runtime state keys | [`extension.js`](https://github.com/SIDIKICONDE/dusk-office/blob/main/extension.js) — `duskOffice.previousTheme`, `favoriteTheme`, `workspaceTheme`, title bar / product icon restore keys |
| Build & theme pipeline | [MAINTENANCE.md](./MAINTENANCE.md) |

### Optional: secondary Git gutter (staged)

The theme JSON schema does not allow `editorGutter.*SecondaryBackground` keys. To still color **staged** stripes differently from **unstaged**, add `workbench.colorCustomizations` for your active theme label, for example **Dusk Office**:

```json
"workbench.colorCustomizations": {
  "[Dusk Office]": {
    "editorGutter.modifiedSecondaryBackground": "#fbbf2499",
    "editorGutter.addedSecondaryBackground": "#22c55e99",
    "editorGutter.deletedSecondaryBackground": "#ef444499"
  }
}
```

Use matching accent hexes if you use another variant.

## Terminal Colors

Paths such as `scripts/palettes-extended-ui.json` and `merge-extended-ui-colors.mjs` live in the **[extension repository](https://github.com/SIDIKICONDE/dusk-office)**.

Integrated terminal uses **`terminal.background`** = **`panel`** and **`terminal.foreground`** = **`fg`** from each entry in `scripts/palettes-extended-ui.json` (applied by `merge-extended-ui-colors.mjs`). ANSI slots map to the same palette (errors, accents, success, etc.), so each **dark variant** keeps a coherent "profile" (fond + texte + couleurs d'échappement).

### Dark variants — `panel` and default text (`fg`)

| Variant | `panel` (terminal bg) | `fg` (default terminal text) |
|---------|------------------------|------------------------------|
| Midnight | `#010102` | `#d1e0e8` |
| Abyss | `#030810` | `#cfe8f0` |
| Reef | `#011018` | `#cffafe` |
| Bay | `#051c14` | `#ecfdf5` |
| Dawn | `#243a4e` | `#fafcff` |
| Mist | `#202c3a` | `#f4f9fc` |
| Ash | `#1e2228` | `#e5e7eb` |
| Nebula | `#0c0618` | `#f3e8ff` |
| Nocturne | `#1e1f29` | `#f8f8f2` |
| Finance | `#0a1219` | `#e8e6e3` |
| Corporate | `#181a1c` | `#c5c8c6` |

**Light** and **Ivory** themes use a light `terminal.background`; ANSI values still follow the merge pipeline but are tuned for dark shells — contrast on light panels is not the same as on dark `panel` values above.

### Default ANSI mapping (Dusk Office / Abyss family)

All themes include a complete ANSI color palette (exact hex depends on variant):

| Color | Standard | Bright |
|-------|----------|--------|
| Black | `#1e1e1e` | `#6b7280` |
| Red | `#f87171` | `#fca5a5` |
| Green | `#22c55e` | `#86efac` |
| Yellow | `#fbbf24` | `#fde047` |
| Blue | `#38bdf8` | `#93c5fd` |
| Magenta | `#c084fc` | `#f0abfc` |
| Cyan | `#22d3ee` | `#67e8f9` |
| White | `#e5e5e5` | `#fafafa` |

Terminal cursor and selection colors match the active theme accent.

### Check contrast locally

After cloning [SIDIKICONDE/dusk-office](https://github.com/SIDIKICONDE/dusk-office) and regenerating themes, run:

```bash
npm run verify:terminal
```

This verifies **`terminal.foreground`** vs **`terminal.background`** (WCAG **4.5:1** for default text) and, for **`vs-dark`** / **`hc-black`** themes, ANSI colors (except black slots) at **≥ 2.9:1** vs the terminal background. **Light** themes (`uiTheme: vs`) only check the default terminal text contrast — ANSI checks are skipped because the same hexes target dark terminal backgrounds.

Quick “if you want…” picks and the full theme table: **[README — Pick a Variant](./README.md#pick-a-variant)** and [Included Themes](#included-themes) above.

---

## Also by the same developer

See **[README — Also by the same developer](./README.md#also-by-the-same-developer)** (NythyCleaner and links).