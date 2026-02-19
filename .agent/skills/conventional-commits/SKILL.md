---
name: conventional_commits
description: Standardizes git commit messages using Conventional Commits with icons, a 50-character title limit, and mandatory descriptions.
---

# Conventional Commits Skill

This skill enforces a standardized git commit format to ensure a clean, searchable, and readable project history.

## 📋 Commitment Format

All commits must follow this structure:

```text
<icon> <type>(<scope>): <subject>

[optional body]

[optional footer]
```

### 📏 Constraints
- **Title (Subject)**: Maximum **50 characters**. It must be concise and imperative.
- **Description (Body)**: **Mandatory**. It should explain *why* the change was made and any relevant details.
- **Icon**: Must be placed at the very beginning of the commit message.

## 🛠️ Commit Types and Icons

| Type | Icon | Purpose |
| :--- | :--- | :--- |
| `feat` | ✨ | A new feature |
| `fix` | 🐛 | A bug fix |
| `docs` | 📝 | Documentation only changes |
| `style` | 🎨 | Changes that do not affect the meaning of the code (white-space, formatting, etc.) |
| `refactor` | ♻️ | A code change that neither fixes a bug nor adds a feature |
| `perf` | ⚡️ | A code change that improves performance |
| `test` | ✅ | Adding missing tests or correcting existing tests |
| `build` | 🏗️ | Changes that affect the build system or external dependencies |
| `ci` | 👷 | Changes to CI configuration files and scripts |
| `chore` | 🔧 | Other changes that don't modify src or test files |
| `revert` | ⏪️ | Reverts a previous commit |

## 💡 Examples

### Valid Feature Commit
```text
✨ feat(ui): add theme toggle button

Implemented a React component to switch between light and dark modes.
The preference is stored in localStorage for persistence.
```

### Valid Fix Commit
```text
🐛 fix(logic): prevent null pointer on canvas resize

Added a null check for the canvas element before accessing its context
in the resize handler.
```

## 🚀 How to use
As an AI agent, whenever you are about to perform a commit:
1. Identify the **type** of changes.
2. Select the corresponding **icon**.
3. Draft a **subject** line within 50 characters.
4. Write a detailed **body** (Description).
5. Combine them into the final commit message.
