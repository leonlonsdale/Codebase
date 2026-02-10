# Codebase - An obsidian vault for nerds.

This repository provides a structured framework for a technical knowledge base. It is designed for developers and systems engineers who require a high-performance, automated, and scalable way to manage documentation, code snippets, and conceptual bridges.

## Purpose

The primary objective of this vault is to serve as a definitive source of truth for quick facts and actionable technical tips. It functions simultaneously as a learning resource for newcomers and a high-speed cheat sheet for experienced practitioners. By maintaining atomic notes, the vault ensures that information is granular, easily searchable, and serves as a reliable reminder for complex technical configurations and syntax.

## Contribution Guidelines

Contributions via Pull Requests (PRs) are welcome. For comprehensive instructions on style, formatting, and specific technical workflows, refer to the detailed documentation located in the `00 Meta/Guides` directory.

To maintain the integrity of the system, contributors must adhere to the following standards:

1. **Use Templates:** All new files must be created using the appropriate template from `00 Meta/Templates` (MoC, Topic, Bridge, or Note). These templates pre-configure the necessary YAML properties.
2. **Mandatory Type Definition:** Every new note must define its structural role using exactly one `type/` tag in the metadata.
3. **Backlinking Requirements:** When the assigned type is `type/note` or `type/topic`, the contributor must add explicit backlinks to the appropriate parent MoCs, Topics, or Bridges to maintain the connectivity of the knowledge graph.
4. **Maintain Atomicity:** Ensure your contribution focuses on a single concept or tool. Do not combine unrelated technical instructions into a single file.
5. **Validate Syntax:** Code snippets should be tested and formatted correctly for Shiki highlighting.

## Philosophy: Relational Atomicity

Traditional note-taking relies on deep folder nesting, which inevitably collapses under the weight of cross-platform tools. This vault uses a flat-folder structure for storage but a deep-metadata structure for retrieval.

### Core Principles
1. **Atomicity:** Every note in the Notes directory should cover exactly one specific concept.
2. **Structural Precedence:** Folder paths are determined by Type and Domain metadata. File locations are a result of classification, not manual placement.
3. **The Three-Tag Rule:** Every file is defined by its format (type/), its location (dom/), and its function (cat/).

## Vault Structure

* **00 Meta**: Administrative files, Tag Index, Guides, and **Templates**.
* **01 MoC (Maps of Content)**: High-level dashboards that act as entry points to entire domains.
* **02 Topic**: Mid-level subject hubs connecting MoCs to specific atomic notes.
* **03 Bridge**: Conceptual links that span multiple domains or languages.
* **04 Notes**: The storage engine. Contains unnumbered sub-directories organised by Domain (Coding, Terminals, etc.).

## The Tagging Engine

| Tag Prefix | Cardinality | Purpose | Example |
| :--- | :--- | :--- | :--- |
| type/ | Exactly 1 | Determines the format and root folder. | type/note |
| dom/ | Exactly 1 | Determines the sub-directory in 04 Notes. | dom/term |
| cat/ | 1 or More | Describes function, platform, or usage. | cat/config |
| lang/ | Optional | Identifies technical language. | lang/nix |

## Best Practices: What to do vs. What not to do

### Metadata Assignment
* **Do:** Use the templates provided in `00 Meta/Templates` to ensure YAML compliance.
* **Do:** Use multiple categories to increase searchability (e.g., cat/config and cat/workflow).
* **Don't:** Create new top-level domain tags without updating the Tag Index and Auto Note Mover rules.
* **Don't:** Use plural versions of tags (e.g., use type/note, not type/notes).

### Note Content
* **Do:** Keep notes atomic. If a note covers two distinct topics, split it into two files.
* **Do:** Add bidirectional links (backlinks) to ensure the note is reachable from its parent Topic or MoC.
* **Don't:** Use folders to categorise notes manually. Use tags and let the system handle the organisation.

## Automation and Setup

This vault is optimised for use with Obsidian and two critical plugins:

1. **Auto Note Mover:** The logic engine. It reads the YAML properties and instantly moves the file to the correct directory.
2. **Shiki Highlighter:** The visual engine. It provides professional-calibre syntax highlighting for code blocks.
3. **Templates:** Standardised starting points for MoCs, Topics, Bridges, and Notes are located in `00 Meta/Templates`.

## Workflow
1. Create a new note and apply the relevant **Template** from `00 Meta/Templates`.
2. Populate the Properties (YAML).
3. The Auto Note Mover will move the file to its destination instantly.
4. Add a backlink to the new note in the corresponding parent Topic or MoC.