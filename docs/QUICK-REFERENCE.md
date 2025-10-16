# PM Agents - Quick Reference

**One-page cheat sheet for using the three PM agents**

---

## The 3 Agents

| Agent | File | Use When | Output |
|-------|------|----------|--------|
| **Project PRD Writer** | `agents/project-prd-writer-enhanced-v2.md` | Converting meeting transcripts to full PRDs | Comprehensive project PRD (10-20 pages) |
| **Feature PRD Writer** | `agents/concise-feature-prd-writer.md` | Specifying individual features | Concise feature PRD (3-5 pages) |
| **Feature Extractor** | `agents/prd-feature-extractor.md` | Breaking down project PRDs | Feature list with tasks & priorities |

---

## Quick Start (3 Steps)

### Step 1: Open Claude
Go to [claude.ai](https://claude.ai) and start a new chat

### Step 2: Load Agent
Copy the entire content of the agent file and paste into Claude

### Step 3: Provide Input
```
[Paste your transcript/description]

"Create a [project/feature] PRD from this"
```

---

## Common Commands

### Project PRD Writer
```
"Create a comprehensive project PRD from this meeting transcript"

"Focus on stakeholder conflicts and resolve them explicitly"

"Make this executive-ready for board presentation"
```

### Feature PRD Writer
```
"Create a concise feature PRD for [feature name]"

"Flag any missing information that needs clarification"

"Make this suitable for client, designer, and developer review"
```

### Feature Extractor
```
"Extract all features from this PRD"

"Break down features into development tasks with priorities"

"Ensure complete coverage of all requirements"
```

---

## Typical Workflow

```
1. Meeting with stakeholders
   ↓
2. Use Project PRD Writer (get full project PRD)
   ↓
3. Use Feature Extractor (get feature list)
   ↓
4. Use Feature PRD Writer (for each feature)
   ↓
5. Hand off to development team
```

---

## Pro Tips

✅ **DO:**
- Provide full context before asking
- Answer all clarifying questions
- Iterate on the output
- Save PRDs with descriptive names

❌ **DON'T:**
- Just say "create a PRD" without context
- Ignore missing information warnings
- Use first draft without review
- Forget to specify your audience

---

## File Organization

```
docs/prds/
├── project/           # Project PRDs here
└── features/          # Feature PRDs here
    ├── [project-1]/
    └── [project-2]/
```

---

## Troubleshooting

**Problem:** Generic output
**Solution:** Add more specific details, names, requirements

**Problem:** Too long/short
**Solution:** Ask Claude to adjust length

**Problem:** Agent not following process
**Solution:** Copy ENTIRE agent file including `---` at top

---

## Examples in Repository

- `docs/prds/project/inventory-management-system-prd.md`
- `docs/prds/features/inventory-management/feature-prd-qr-scanning.md`

---

## Need More Help?

📖 Read full guide: `docs/HOW-TO-USE-PM-AGENTS.md`

---

*Quick Reference v1.0*
