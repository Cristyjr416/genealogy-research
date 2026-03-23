# Genealogy Research Skill for Claude Code

A comprehensive genealogy research assistant skill that turns Claude into a systematic family history researcher using the [Genealogical Proof Standard](https://www.bcgcertification.org/ethics-standards/genealogical-proof-standard/) (GPS) methodology.

## What It Does

- **Analyzes historical documents**: Reads handwritten records in Latin, Polish, Russian, German, French, English, and other European languages
- **Manages an Obsidian knowledge base**: Creates and maintains People, Places, Documents, and Events files with cross-references
- **Tracks research progress**: Maintains PROCESS.md with completed actions, pending tasks, negative results, and evidence levels
- **Guides systematic search**: Recommends specific databases, parishes, and parameters based on region and time period
- **Handles naming complexity**: Understands patronymics, declension, transliteration, and scribe-era spelling variations across cultures
- **Works with GEDCOM**: Import/export standard genealogy data format
- **Covers 15+ countries**: Database references for Poland, Germany, Russia, UK, Ireland, France, Italy, Scandinavia, Czech Republic, Hungary, USA, Canada, and more

## Installation

### Claude Code (CLI)

```bash
claude install-skill /path/to/genealogy-research
```

Or copy the `genealogy-research/` directory to `~/.claude/skills/`.

### Manual

Copy the skill directory into your Claude Code skills location:

```
~/.claude/skills/genealogy-research/
├── SKILL.md
└── references/
    ├── databases-by-region.md
    ├── naming-conventions.md
    ├── common-pitfalls.md
    └── vault-templates.md
```

## Usage

Start a conversation with Claude Code in your family history project directory. The skill triggers automatically when you:

- Share a scan or photo of a historical document
- Ask about ancestors or family history
- Work with an Obsidian vault containing genealogical data
- Mention parish records, vital records, or census data
- Work with GEDCOM files

### Example Starter Prompt

```
You are a genealogy research partner. My project is in this directory.

Region: Poland / Russian Empire partition, 19th century
Languages: Polish, Russian, Latin
Obsidian vault: Chronicles/

I have scans of parish registers in materials/skany/.
Start by analyzing the documents and building a research plan.
```

## What's Included

| File | Purpose |
|------|---------|
| `SKILL.md` | Core methodology, workflow, capabilities |
| `references/databases-by-region.md` | 80+ databases across 15+ countries |
| `references/naming-conventions.md` | Surname variations in Slavic, Germanic, Romance, Scandinavian, Jewish naming traditions |
| `references/common-pitfalls.md` | Indexing gaps, parish reassignments, calendar issues, identity confusion |
| `references/vault-templates.md` | Obsidian templates for People, Places, Documents + PROCESS.md and AGENT.md formats |

## Methodology

Based on the Genealogical Proof Standard (GPS):

1. **Evidence levels**: Every fact tagged as Proven / Probable / Possible / Unproven
2. **Source hierarchy**: Original > Derivative > Narrative
3. **Planning before searching**: Document knowns, formulate questions, identify sources
4. **Negative results**: "Not found" is valuable evidence — always documented
5. **Human + AI workflow**: Human provides documents and performs web searches; AI analyzes, connects, and maintains the knowledge base

## Origin

Born from a real family history project that reconstructed 8 generations (1760s–2013) across Poland, Russia, New Zealand, and the USA in two days of systematic research. The methodology proved effective enough to generalize.

## License

MIT
