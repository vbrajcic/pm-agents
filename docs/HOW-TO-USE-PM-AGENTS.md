# How to Use PM Agents

**Complete guide for product managers and teams to use the three core PM agents**

---

## Overview

This repository contains 3 powerful AI agents designed to help product managers create professional, comprehensive PRDs (Product Requirements Documents):

1. **Project PRD Writer** - Creates complete project PRDs from meetings/transcripts
2. **Feature PRD Writer** - Writes detailed feature specifications
3. **Feature Extractor** - Breaks down project PRDs into developable features

---

## Prerequisites

### What You Need:
- **Claude Account** (claude.ai) - Free or Pro
- **This repository** cloned to your computer
- **Meeting transcripts, notes, or feature ideas** to work with

### Setup (One-Time):
1. Go to [claude.ai](https://claude.ai)
2. Sign in or create an account
3. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/pm-agents.git
   cd pm-agents
   ```

---

## The Three Agents

### 🎯 Agent 1: Project PRD Writer (Enhanced V2)

**What it does:** Creates executive-ready, comprehensive project PRDs from meeting transcripts, brainstorming sessions, or stakeholder discussions.

**When to use it:**
- After a kickoff meeting with stakeholders
- When you have meeting transcripts to convert to PRDs
- When starting a new project that needs documentation
- When you need a board-ready PRD for presentation

**What you get:**
- Complete project PRD with executive TL;DR
- Stakeholder conflict resolution documented
- Risk assessment and mitigation strategies
- Implementation roadmap with phases
- Success metrics and measurement plan

**Agent file:** `agents/project-prd-writer-enhanced-v2.md`

---

### ✏️ Agent 2: Feature PRD Writer (Concise)

**What it does:** Creates focused, actionable feature specifications that developers, designers, and clients can all understand.

**When to use it:**
- When adding a new feature to an existing product
- When you need detailed specs for a specific capability
- When designers need UX requirements
- When developers need clear acceptance criteria

**What you get:**
- Concise feature specification (not a novel!)
- Clear user flows and acceptance criteria
- Business rules and edge cases
- Data requirements and integrations
- Development task breakdown

**Agent file:** `agents/concise-feature-prd-writer.md`

---

### 🔍 Agent 3: Feature Extractor

**What it does:** Analyzes a project PRD and extracts all individual features, organizing them for development teams.

**When to use it:**
- After completing a project PRD
- When planning sprints and development phases
- When you need to break down a big project
- When estimating development effort

**What you get:**
- Complete list of features from your PRD
- Each feature broken into sub-tasks
- Priority levels (P0, P1, P2, P3)
- Development complexity estimates
- Requirement traceability matrix

**Agent file:** `agents/prd-feature-extractor.md`

---

## Quick Start Guide

### Method 1: Using Claude Projects (Recommended)

**Step 1: Create a Claude Project**
1. Go to [claude.ai](https://claude.ai)
2. Click "Projects" in the sidebar
3. Click "+ New Project"
4. Name it: "PM Agents"

**Step 2: Add Agent to Project**
1. In your PM Agents project, click "Project Knowledge"
2. Click "Add content"
3. Choose "Paste text"
4. Copy the ENTIRE contents of one of these files:
   - `agents/project-prd-writer-enhanced-v2.md` (for Project PRD Writer)
   - `agents/concise-feature-prd-writer.md` (for Feature PRD Writer)
   - `agents/prd-feature-extractor.md` (for Feature Extractor)
5. Click "Save"

**Step 3: Use the Agent**
1. Start a new conversation in the project
2. Paste your meeting transcript or feature description
3. Ask: "Create a project PRD from this transcript" (or similar)
4. The agent will follow its process and create your document

---

### Method 2: Using Individual Conversations (Simpler)

**Step 1: Start a New Conversation**
1. Go to [claude.ai](https://claude.ai)
2. Click "+ New Chat"

**Step 2: Load the Agent**
1. Open one of the agent files in a text editor:
   - `agents/project-prd-writer-enhanced-v2.md`
   - `agents/concise-feature-prd-writer.md`
   - `agents/prd-feature-extractor.md`
2. Copy the ENTIRE file content
3. Paste it into Claude
4. Send the message

**Step 3: Use the Agent**
1. In the same conversation, provide your input:
   - Meeting transcript
   - Feature description
   - Project PRD (for extractor)
2. Ask the agent to create your document
3. Review and iterate with Claude

---

## Complete Workflow Example

### Scenario: Building a New Inventory Management System

**Week 1: Create Project PRD**

1. **Hold kickoff meeting** with stakeholders
   - Record or transcribe the meeting
   - Gather all requirements, conflicts, constraints

2. **Use Project PRD Writer:**
   ```
   [Paste entire meeting transcript]

   "Please create a comprehensive project PRD from this kickoff meeting transcript.
   We need executive-ready documentation that includes stakeholder conflict resolution
   and a detailed implementation roadmap."
   ```

3. **Review & Iterate:**
   - Claude asks clarifying questions
   - You provide answers
   - Claude generates complete PRD
   - Save to: `docs/prds/project/inventory-management-prd.md`

**Week 2: Extract Features**

4. **Use Feature Extractor:**
   ```
   [Paste the project PRD you just created]

   "Extract all features from this project PRD and break them down for development.
   Ensure complete coverage of all requirements."
   ```

5. **Get Feature List:**
   - Claude identifies all features
   - Provides priority levels (P0, P1, P2, P3)
   - Breaks each into development tasks
   - Save the feature list

**Week 3-N: Create Feature PRDs**

6. **For Each Feature, Use Feature PRD Writer:**
   ```
   Feature: User Authentication with Role-Based Access Control

   Context: Part of inventory management system. We need authentication
   that supports 3 roles: Employee, Manager, Admin.

   "Create a concise feature PRD for this authentication feature."
   ```

7. **Review & Hand Off:**
   - Claude creates detailed feature PRD
   - Review with designers and developers
   - Use for sprint planning
   - Save to: `docs/prds/features/inventory-management/feature-prd-authentication.md`

---

## Common Use Cases

### Use Case 1: You have a meeting transcript

```
1. Open Claude
2. Load Project PRD Writer agent
3. Paste your transcript
4. Say: "Create a comprehensive project PRD from this meeting transcript"
5. Answer any clarifying questions
6. Get your complete PRD!
```

### Use Case 2: You need a feature spec

```
1. Open Claude
2. Load Feature PRD Writer agent
3. Describe your feature
4. Say: "Create a concise feature PRD for this"
5. Review and iterate
6. Share with your team!
```

### Use Case 3: You need to plan development

```
1. Open Claude
2. Load Feature Extractor agent
3. Paste your project PRD
4. Say: "Extract all features and break them down for development"
5. Get your feature list with priorities
6. Use for sprint planning!
```

---

## Tips for Best Results

### General Tips:
1. **Start with Context** - Always provide background before asking for output
2. **Iterate** - Claude will ask clarifying questions - answer them!
3. **Review & Refine** - First draft is rarely perfect - ask for improvements
4. **Save Everything** - Keep PRDs in version control (git)
5. **Use Markdown** - All agents output markdown for easy formatting

### Project PRD Writer Tips:
- Include actual stakeholder quotes from meetings
- Mention specific dates and timelines
- Highlight any conflicts or disagreements
- Provide budget/resource constraints if known

### Feature PRD Writer Tips:
- Be specific about user types and roles
- Include edge cases and error scenarios
- Mention integrations with other features
- Flag anything you're uncertain about

### Feature Extractor Tips:
- Feed it complete, well-structured PRDs
- Request traceability to original requirements
- Ask for priority justifications
- Use output for roadmap and sprint planning

---

## File Organization

Keep your outputs organized:

```
pm-agents/
├── docs/
│   └── prds/
│       ├── project/
│       │   ├── inventory-management-prd.md
│       │   └── employee-onboarding-prd.md
│       └── features/
│           ├── inventory-management/
│           │   ├── feature-prd-authentication.md
│           │   ├── feature-prd-qr-scanning.md
│           │   └── feature-prd-reporting.md
│           └── employee-onboarding/
│               ├── feature-prd-profile-setup.md
│               └── feature-prd-task-workflow.md
```

---

## Troubleshooting

### "Agent doesn't follow the process"
**Solution:** Make sure you pasted the ENTIRE agent file (including the YAML front matter at the top with `---`)

### "Output is too generic"
**Solution:** Provide more specific context. Include actual data, names, requirements, not just "create a PRD for an app"

### "Missing information in PRD"
**Solution:** That's intentional! Agents flag what's missing. Provide the missing info and regenerate.

### "PRD is too long/short"
**Solution:** Ask Claude to adjust:
- "Make this more concise, focus on essentials"
- "Expand this with more detail on [specific section]"

### "Need different format"
**Solution:** All agents output Markdown. You can ask Claude to convert to:
- "Convert this to a Google Docs outline"
- "Format this as a Confluence page"
- "Create a Jira epic with subtasks from this"

---

## Examples & Templates

Check the `docs/prds/` folder for complete examples:

### Project PRD Examples:
- `docs/prds/project/inventory-management-system-prd.md`
- `docs/prds/project/employee-onboarding-portal-prd.md`

### Feature PRD Examples:
- `docs/prds/features/inventory-management/feature-prd-qr-scanning.md`
- `docs/prds/features/employee-onboarding/onboarding-feature-prd-task-workflow.md`

---

## FAQ

**Q: Do I need to pay for Claude?**
A: Free tier works fine. Pro gives you higher usage limits.

**Q: Can I use these with ChatGPT or other AI?**
A: These agents are optimized for Claude, but you can try adapting them.

**Q: How long does it take?**
A: Project PRD: 10-15 minutes. Feature PRD: 5 minutes. Extraction: 5 minutes.

**Q: Can I modify the agents?**
A: Yes! Edit the `.md` files in `agents/` folder to customize behavior.

**Q: Do I need to be technical?**
A: No! These agents are designed for product managers, not developers.

**Q: Can multiple people use this?**
A: Yes! Each person just needs their own Claude account.

**Q: What if my PRD has sensitive information?**
A: Claude's data usage policy: conversations are not used for training. For extra security, use Claude for Work.

---

## Getting Help

**Issues?**
- Check the troubleshooting section above
- Review example PRDs in `docs/prds/`
- Ask Claude directly: "I'm having trouble with [specific issue]"

**Questions?**
- Create an issue in this repository
- Contact your PM team lead

---

## Next Steps

1. ✅ Set up Claude account at claude.ai
2. ✅ Choose which agent you need
3. ✅ Follow Quick Start Guide above
4. ✅ Create your first PRD
5. ✅ Share with your team!

**Ready to get started?**

Choose your path:
- **New Project?** → Use Project PRD Writer first
- **New Feature?** → Use Feature PRD Writer directly
- **Break Down Project?** → Use Feature Extractor

---

*Last Updated: January 2025*
*Version: 1.0*
