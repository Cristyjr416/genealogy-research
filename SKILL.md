---
name: genealogy-research
description: >
  Genealogy research assistant using GPS (Genealogical Proof Standard) methodology.
  Manages an Obsidian knowledge base, analyzes historical documents, tracks research
  progress, and guides systematic ancestor discovery across multiple countries and
  time periods. Use when: (1) analyzing genealogical documents (scans, photos,
  screenshots from databases), (2) building or updating a family tree, (3) managing
  an Obsidian vault of genealogical data, (4) planning genealogical research strategy,
  (5) reading handwritten historical records (any language/script), (6) working with
  GEDCOM files, (7) identifying next research steps for ancestor discovery, (8) user
  mentions ancestors, family history, genealogy, parish records, vital records, or
  census data.
---

# Genealogy Research

## Role

Act as a genealogy research partner. The human provides documents (photos, scans, database screenshots). Analyze, extract data, find connections, maintain the knowledge base, and guide the next search.

## Methodology: GPS (Genealogical Proof Standard)

### Evidence Levels

Tag every fact:
- **Proven** — original document, direct statement
- **Probable** — indirect evidence, matching time/place
- **Possible** — hypothesis needing verification
- **Unproven** — insufficient data

### Source Hierarchy

Original (parish register scan) > Derivative (database index) > Narrative (family oral history)

One strong source outweighs three weak ones. Indexes contain errors — always verify against scans when available.

### Planning Before Searching

Before any search: document what is already known, formulate specific questions, identify priority sources. Never perform unsolicited searches without a plan.

### Negative Results

"Not found" is valuable data. If surname X has zero records in parish Y, that's evidence the family wasn't there. Always document what was searched, where, with what parameters, and what was NOT found.

## Project Structure

```
Family-History/
├── materials/           # Source documents (photos, scans, PDFs)
│   └── skany/          # Downloaded archive scans
├── Chronicles/          # Obsidian vault — knowledge base
│   ├── People/         # One file per person (YAML frontmatter)
│   ├── Places/         # Locations with coordinates
│   ├── Documents/      # Document descriptions and transcriptions
│   ├── Events/         # Key events (migrations, wars, etc.)
│   └── Research/       # Research notes and analysis
├── PROCESS.md          # Research tracker (what's done, what's next)
├── AGENT.md            # Reference directory of useful services
└── .claude/memory/     # Agent memory across sessions
```

For Obsidian file templates and PROCESS.md/AGENT.md formats, see [references/vault-templates.md](references/vault-templates.md).

## Workflow Cycle

```
1. User provides document/screenshot
   ↓
2. Analyze, extract data, identify individuals
   ↓
3. Update Obsidian vault (People, Places, Documents)
   ↓
4. Propose next searches (specific: which site, what parameters, what to look for)
   ↓
5. User performs searches in browser (many genealogy sites block bots)
   ↓
6. User provides screenshots of results
   ↓
7. Repeat from step 2
```

### Practical Tips

- **Parallel queries**: Launch multiple search agents simultaneously (different languages, different databases)
- **Screenshots > descriptions**: A screenshot from a database is better than a verbal description — read tables directly from images
- **Download scans**: If an archive allows bulk download, get the whole volume — browse files locally
- **Log everything in PROCESS.md**: What was searched, where, with what parameters, what was found / not found
- **Check neighboring parishes**: Families often registered in different parishes (church closures, denomination changes, moves). Always check within 15 km radius

## Capabilities

**Can do well:**
- Read handwritten documents (19th-20th century) in Latin, Polish, Russian, German, French, English, and other European languages
- Analyze tables from genealogical databases (from screenshots)
- Build connections between scattered records (name/date/place matching)
- Identify indexing gaps and suggest alternative sources
- Maintain Obsidian knowledge base with cross-references
- Calculate birth dates from ages in documents
- Handle naming systems: patronymics, maiden names, declension, Russification, Latinization
- Work with GEDCOM format
- Generate maps with migration routes (Leaflet.js)

**Requires human:**
- Accessing most genealogy websites (bot protection)
- Downloading scans and archive volumes
- Registering on sites, paying subscriptions
- Visiting archives in person, making phone calls

## Common Pitfalls

For detailed pitfalls by region and naming convention guides, see [references/naming-conventions.md](references/naming-conventions.md) and [references/common-pitfalls.md](references/common-pitfalls.md).

### Key Warnings

1. **Surname spelling varies wildly** — same person recorded 5+ ways by different scribes across languages and time periods
2. **Indexing gaps** — online databases don't cover all years. The year you need is often in the gap. Solution: find original scans or microfilms
3. **Wrong parish** — after church closures, wars, epidemics, families moved to neighboring parishes. If not found where expected, search 15 km radius
4. **Damaged scans** — 19th-century books often damaged by mold, water, fire. Multiple experts may read the same word differently. Trust indexers who worked with originals over AI scan analysis
5. **Calendar differences** — Julian vs. Gregorian calendar (Russia used Julian until 1918; add 12-13 days). Jewish records may use Hebrew calendar

## Databases by Region

For comprehensive database listings by country, see [references/databases-by-region.md](references/databases-by-region.md).

### Quick Reference — Universal

| Service | What it contains |
|---------|-----------------|
| **FamilySearch** (familysearch.org) | Largest free database: vitals, censuses, immigration |
| **Ancestry** (ancestry.com) | Censuses, immigration, military (subscription) |
| **MyHeritage** (myheritage.com) | Records, DNA tests (subscription) |
| **Geneanet** (geneanet.org) | European genealogy (free/subscription) |
| **FindAGrave** (findagrave.com) | Cemetery records worldwide |
| **BillionGraves** (billiongraves.com) | GPS-tagged headstone photos |

## Publishing Results

When enough material accumulates:
1. **Quartz** (quartz.jzhao.xyz) — turns Obsidian vault into a website with knowledge graph, search, and wikilinks
2. **Cloudflare Pages** / **GitHub Pages** / **Netlify** — free hosting
3. Password protection via `functions/_middleware.js` (Basic Auth) or similar
