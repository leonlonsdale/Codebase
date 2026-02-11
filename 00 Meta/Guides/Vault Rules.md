---
type: meta
tags: [type/meta]
---
# Vault Rules

## Description

This note defines the structural and formatting standards for this vault. Adherence to these rules ensures a clean, professional, and scalable environment for technical documentation.

## Structural Hierarchy

The vault operates on a strict top-down flow:
1. **Maps of Content (MoC):** The primary entry points for broad domains.
2. **Topics:** Mid-level nodes that group related sub-topics or atomic notes.
3. **Notes:** Leaf nodes containing pure technical content.

## Linking Conventions

* **Parental Ownership:** MoCs and Topics must explicitly link to their children to maintain the navigation path.
* **Leaf Node Independence:** Atomic notes (leaf nodes) must not contain reverse links to parents. Use the **Backlinks** pane for upward navigation.
* **Directness:** Avoid "random" links within prose; keep navigation confined to the designated sections of MoCs and Topics.

## Formatting Standards

* **Heading Hierarchy:** * `# Title` (H1) is reserved for the file name.
    * `## Section` (H2) is for primary divisions (Description, Examples, Topics).
    * Never skip heading levels (e.g., do not place an H3 directly under an H1).
* **Code:** Use fenced code blocks with the appropriate language identifier for syntax highlighting.

## File Management

* **Storage:** All system documentation and templates reside in `00 Meta`.
* **Assets:** All images, diagrams, and PDFs must be stored in `00 Meta/Assets`.
* **Templates:** Every new file must be generated from its respective template to ensure structural integrity.

## Tagging Protocol

* **Location:** Tags are stored in the Properties (YAML) frontmatter.
* **Format:** Lowercase, singular, and nested (e.g., `#type/note`, `#lang/js`).
* **Definition:** Refer to the **[[Tag Index]]** before creating new tags.

## Note Naming Protocol

- **MoCs** and **Topics** names must clearly define the topic. There must be no question as to what the topic is. It must not cover more than one topic. If more than one topic could be covered, make one a sub-topic.
- **Notes** should be named in the format `topic - note subject` with the topic name pre-fixing the subject. For example, `javascript - functions`. Abbreviations may be used for the prefix where the topic is long, for example: `Data Structures and Algorithms` may be abbreviated to `DSA`. 