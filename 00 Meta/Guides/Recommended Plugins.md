# Recommended Plugins

## Description

This note outlines the core plugins required to maintain the vault's automation, structural integrity, and technical readability.

---

## 1. Auto Note Mover

**Purpose:** Automatically files notes into the correct directory based on the tags defined in the Tag Index.

### Configuration Logic
Rules must be ordered from **most specific to most general**. The plugin stops at the first match it finds.

#### Priority 1: Structural Overrides (Type Tags)
These ensure that structural files are pulled into the numbered root folders immediately.

| Trigger Tag    | Target Folder    |
| :------------- | :--------------- |
| `#type/moc`    | `01 MoC`         |
| `#type/topic`  | `02 Topic`       |
| `#type/bridge` | `03 Bridge`      |
| `#type/meta`   | `00 Meta/Guides` |

#### Priority 2: Domain Routing (Domain Tags)
These rules apply only to `#type/note` or `#type/snippet` files. They route the file into the unnumbered sub-directories within the Notes folder.

| Trigger Tag | Target Folder                |
| :---------- | :--------------------------- |
| `#dom/code` | `04 Notes/Coding`            |
| `#dom/os`   | `04 Notes/Operating Systems` |
| `#dom/term` | `04 Notes/Terminals`         |
| `#dom/edit` | `04 Notes/Code Editors`      |
| `#dom/cli`  | `04 Notes/CLI Tools`         |

### Key Plugin Settings

- **Trigger:** Set to `Automatic`.
- **Use Tag:** Enabled.
- **Check on Start:** Enabled.
- **Excluded Folders:** To prevent the plugin from moving your configuration files or templates, you **must** add the following to the excluded list:
    - `00 Meta`
    - `00 Meta/Templates`

---

## 2. Shiki Highlighter

**Purpose:** Replaces the standard Prism.js highlighter with **Shiki**, providing VS Code-calibre syntax highlighting.

### Why this is required

As an atomic technical vault, readability of code is paramount. Shiki provides superior tokenisation for:

- **Golang:** Handles interfaces and structs with proper colour differentiation.
- **Nix:** Essential for the complex syntax of NixOS flakes and expressions.
- **TypeScript/JS:** Accurate highlighting for modern ES6+ syntax.

### Recommended Settings

- **Theme:** `vitesse-dark` or `github-dark` (ensure consistency across all devices).
- **Default Language:** Set to `plain text` to avoid false positives.
- **Languages to Pre-load:** `go`, `nix`, `javascript`, `typescript`, `bash`, `yaml`, `json`.

---

## Usage Summary

1. **Creation:** Create a new note in the root directory.
2. **Metadata:** Fill in the Properties (YAML).
    * *Example:* `type: note`, `dom: code`, `lang: go`.
3. **Execution:** **Auto Note Mover** will move the file to `04 Notes/Coding` instantly.
4. **Display:** Use standard Markdown code blocks. **Shiki** will render them with high-fidelity highlighting based on the language tag used.