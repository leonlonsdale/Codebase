---
type: meta
tags:
  - type/meta
AutoNoteMover: disable
---
# Tag Index

## Description

This note serves as the definitive reference for tags within this vault. It ensures that the top-down hierarchy remains consistent and that metadata does not clash with technical content. It also functions as the logic engine for **Auto Note Mover**.

> [!tip] Setup Recommendation
> To ensure the vault functions as intended, please visit the [[Recommended Plugins]] note to install and configure the necessary automation tools.

## Tagging Cardinality

To maintain a clean and automated structure, every note must adhere to the following rules: 

* **Exactly one `#type/` tag:** Defines the note's structural role. 
* **Exactly one `#dom/` tag:** Defines the note's storage location (for atomic notes). 
* **Multiple `#cat/` tags (Optional):** You may assign as many categories as needed to describe the note's functional purpose (e.g., `#cat/config` and `#cat/workflow`).
## Type Tags

These tags define what a note **is**. Every note should have exactly one type tag.

| Tag           | Target Folder | Purpose                                                           |
| :------------ | :------------ | :---------------------------------------------------------------- |
| #type/moc     | `01 MoC`      | High-level dashboards (Map of Content) that list Topics.          |
| #type/topic   | `02 Topic`    | Mid-level notes that group related Sub-topics or atomic Notes.    |
| #type/bridge  | `03 Bridge`   | Conceptual notes linking logic across multiple languages/domains. |
| #type/note    |               | Leaf nodes. Detailed technical references with code.              |
| #type/snippet |               | Minimalist notes containing code with little to no prose.         |
| #type/meta    | `00 Meta`     | Vault-specific documentation and organisational rules.            |

## Domain Tags

These tags define the **Sub-directory** within the `04 Notes` folder for atomic content. These sub-directories are **not** numbered.

| Tag         | Target Sub-directory         | Domain Scope                                   |
| :---------- | :--------------------------- | :--------------------------------------------- |
| #dom/code   | `04 Notes/Coding`            | General programming, logic, and syntax.        |
| #dom/os     | `04 Notes/Operating Systems` | All OS-specific notes (Linux, macOS, Windows). |
| #dom/term   | `04 Notes/Terminals`         | Terminal emulators, shells, and multiplexers.  |
| #dom/editor | `04 Notes/Code Editors`      | IDEs and text editors (VS Code, Neovim).       |
| #dom/cli    | `04 Notes/CLI Tools`         | Command-line utilities and standalone tools.   |

## Category Tags

These tags define functional roles or specific platforms. They allow for precise filtering within domains.

| Tag           | Purpose                                                |
| :------------ | :----------------------------------------------------- |
| #cat/linux    | Specific to Linux distributions and kernel.            |
| #cat/macos    | Specific to macOS system and Apple software.           |
| #cat/windows  | Specific to Windows OS and PowerShell environment.     |
| #cat/config   | Configuration files, dotfiles, and setup instructions. |
| #cat/install  | Installation steps and package management.             |
| #cat/logic    | Algorithms, patterns, and core programming theory.     |
| #cat/env      | Paths, environment variables, and shell setups.        |
| #cat/history  | Authorship, "About" info, and origins of a tool.       |
| #cat/workflow | Personal processes and usage methodologies.            |

## Language Tags

Identifies the specific technology or language.

| Tag        | Purpose                                  |
| :--------- | :--------------------------------------- |
| #lang/js   | JavaScript specific content.             |
| #lang/ts   | TypeScript specific content.             |
| #lang/go   | Golang specific content.                 |
| #lang/py   | Python specific content.                 |
| #lang/nix  | Nix Expression Language / NixOS content. |
| #lang/bash | Bash / Shell scripting.                  |
| #lang/css  | Styling and CSS specific content.        |

## Structural Rules

* **Format:** Always lowercase and singular.
* **Nesting:** Use the `group/subgroup` syntax to keep the Tag Pane organised.
* **Placement:** Tags must be placed in the Properties (YAML) section.
* **Automation:** To prevent a note from being moved, add `AutoNoteMover: disable` to the Properties.