# Session Knowledge Base

**Living repository of project learnings, best practices, and reusable code patterns**

---

## 🎯 Purpose

This repository serves as a **cumulative knowledge base** that gets smarter with every project. It captures:
- ✅ Proven patterns and best practices
- ✅ Common pitfalls and how to avoid them
- ✅ Reusable code snippets and components
- ✅ Decision frameworks and guidelines
- ✅ Detailed session summaries for reference

---

## 📚 Quick Start

### Starting a New Project
```bash
/project-init
```
Loads the master knowledge base, checklist, and relevant patterns to guide your project.

### Ending a Session
```bash
/summarize-session
```
Auto-generates comprehensive summary, extracts learnings, updates master files, and pushes to GitHub.

---

## 📁 Repository Structure

```
session-knowledge-base/
├── KNOWLEDGE-BASE.md           # Master reference - best practices, pitfalls, guidelines
├── PROJECT-CHECKLIST.md        # Standard checklist for all new projects
├── README.md                   # This file
│
├── code-library/              # Reusable code patterns organized by language
│   ├── bash/                  # Shell scripts and patterns
│   ├── javascript/            # JS/React/Node patterns
│   ├── n8n/                   # N8N workflow patterns and nodes
│   └── python/                # Python utilities and patterns
│
├── docs/                      # Documentation and guides
│   ├── patterns/              # Design patterns and approaches
│   └── sessions/              # Detailed session summaries by project type
│       ├── n8n-workflow/      # N8N workflow projects
│       ├── integration/       # Integration projects
│       ├── frontend/          # Frontend projects
│       ├── data-pipeline/     # Data pipeline projects
│       ├── analytics/         # Analytics/Tableau projects
│       ├── agent-design/      # Agentic systems
│       ├── a2a-protocol/      # A2A protocol implementations
│       └── other/             # Misc projects
│
├── mcp-servers/               # MCP server configurations and docs
│
└── quality-rules/             # Quality criteria and LLM-judge rules
    └── compliance/            # Compliance requirements
```

---

## 🚀 Core Files

### [KNOWLEDGE-BASE.md](./KNOWLEDGE-BASE.md)
**Master reference document** synthesizing learnings across all projects:
- Core principles that guide decisions
- Best practices by category
- Common pitfalls with solutions
- Decision frameworks
- Preferred approaches
- Tool & technology guidelines

### [PROJECT-CHECKLIST.md](./PROJECT-CHECKLIST.md)
**Comprehensive checklist** for project initialization and closeout:
- Pre-project setup steps
- Configuration management
- Development guidelines
- Testing & validation
- Documentation requirements
- Project-type specific checklists

---

## 🔄 Workflow

### 1. Project Initialization
1. Run `/project-init` to load knowledge base
2. Review `KNOWLEDGE-BASE.md` for relevant patterns
3. Check `code-library/` for reusable components
4. Adapt `PROJECT-CHECKLIST.md` to your project
5. Search `docs/sessions/` for similar past projects

### 2. During Development
- Reference code library before writing new solutions
- Document decisions and trade-offs as you go
- Extract reusable patterns for future use
- Follow established naming conventions
- Commit regularly with clear messages

### 3. Session Closeout
1. Run `/summarize-session` (auto-generates summary)
2. Summary saved to `docs/sessions/[project-type]/`
3. Key learnings auto-extracted to `KNOWLEDGE-BASE.md`
4. New patterns added to `code-library/`
5. Everything committed and pushed to GitHub

---

## 📊 Knowledge Evolution

This repository **learns from every project**:

### Individual Session Summaries
- Detailed capture in `docs/sessions/[project-type]/`
- Filename format: `YYYY-MM-DD-project-name-summary.md`
- Full context preserved for future reference

### Master Knowledge Base
- Living document in `KNOWLEDGE-BASE.md`
- Synthesizes patterns across sessions
- Updated automatically after each `/summarize-session`
- Quarterly reviews to remove outdated content

### Code Library
- Proven, reusable patterns organized by language
- Each pattern documented with:
  - Use case
  - Implementation
  - When to use / when not to use
  - Variations and adaptations

---

## 🎓 Learning from Sessions

Every session summary contributes to the knowledge base:

**Automatic extraction includes:**
- ✅ New best practices → `KNOWLEDGE-BASE.md`
- ✅ Gotchas & solutions → `KNOWLEDGE-BASE.md` pitfalls section
- ✅ Reusable code → `code-library/`
- ✅ Configuration patterns → `KNOWLEDGE-BASE.md` guidelines
- ✅ Decision rationales → `KNOWLEDGE-BASE.md` frameworks

---

## 🛠️ Custom Commands

### `/project-init`
Loads master knowledge base at project start:
- Displays key principles and best practices
- Shows project checklist
- Surfaces relevant code patterns
- Provides quick reference guide

### `/summarize-session`
Auto-generates comprehensive session summary:
- Creates detailed session summary
- Saves to appropriate `docs/sessions/` folder
- Extracts learnings to master files
- Commits and pushes to GitHub
- **Checks review dates** and prompts if reviews are due
- Dual storage: local + remote

### `/knowledge-review`
Conducts scheduled reviews to keep knowledge base fresh:
- Checks `.review-tracker.json` for review status
- Shows which reviews are overdue (weekly/monthly/quarterly)
- Guides you through review process interactively
- Updates KNOWLEDGE-BASE.md with consolidated learnings
- Updates tracking file and commits changes
- Ensures knowledge base stays relevant and accurate

---

## 📈 Use Cases

### When Starting a New Project
- Load accumulated knowledge with `/project-init`
- Avoid repeating past mistakes
- Leverage proven patterns
- Follow established best practices

### When Making Decisions
- Reference decision frameworks in `KNOWLEDGE-BASE.md`
- Check past sessions for similar situations
- Review trade-offs from previous projects

### When Stuck on a Problem
- Search `docs/sessions/` for similar challenges
- Check `code-library/` for existing solutions
- Review `KNOWLEDGE-BASE.md` pitfalls section

### When Closing a Session
- Run `/summarize-session` for automatic documentation
- Contribute learnings back to the knowledge base
- Ensure patterns are captured for future use

---

## 🔍 Search & Discovery

**Find relevant knowledge:**
```bash
# Search for specific topics in knowledge base
grep -r "error handling" ~/session-knowledge-base/

# Find code patterns by language
ls -la ~/session-knowledge-base/code-library/python/

# Browse sessions by project type
ls -la ~/session-knowledge-base/docs/sessions/n8n-workflow/
```

---

## 🌱 Contributing to Knowledge Base

### Adding New Patterns
1. Document in appropriate `code-library/` subfolder
2. Include use case and implementation
3. Add entry to `KNOWLEDGE-BASE.md` if widely applicable
4. Reference from relevant session summaries

### Updating Best Practices
1. Edit `KNOWLEDGE-BASE.md` directly
2. Update "Last Updated" date
3. Keep sections concise
4. Archive deprecated approaches

### Improving Checklists
1. Edit `PROJECT-CHECKLIST.md`
2. Add project-specific variations
3. Document new gotchas discovered
4. Keep quality standards current

---

## 🎯 Quality Standards

**Knowledge base content should be:**
- **Actionable**: Guides decisions, not just information
- **Specific**: Concrete examples, not vague generalities
- **Tested**: Only proven approaches included
- **Maintained**: Regularly reviewed and updated
- **Searchable**: Clear keywords and organization

---

## 🔐 Security & Privacy

- **Never commit** sensitive files (.env, credentials, API keys)
- **Redact** sensitive data from session summaries
- **Use placeholders** in code examples for secrets
- **Document** security considerations in relevant sections

---

## 📅 Maintenance

### Regular Reviews (Automated Reminders)
The system tracks review dates in `.review-tracker.json` and reminds you when reviews are due.

- **Weekly** (Every 7 days, ~5-10 min):
  - Quick scan of new sessions
  - Extract immediate learnings
  - `/summarize-session` will prompt when due

- **Monthly** (Every 30 days, ~15-30 min):
  - Consolidate patterns from past month
  - Update code library and checklist
  - Verify links and references

- **Quarterly** (Every 90 days, ~1-2 hours):
  - Comprehensive knowledge base audit
  - Archive outdated content
  - Major restructuring if needed
  - Plan next quarter improvements

**To conduct review**: Run `/knowledge-review` - it will guide you through the process and update tracking automatically.

### Quality Checks
- Remove duplicate patterns
- Consolidate similar approaches
- Update deprecated techniques
- Validate links and references

---

## 🚦 Getting Started

### Initial Setup (One-Time)

**1. Clone the Repository**
```bash
cd ~
git clone https://github.com/gemclass/session-knowledge-base.git
```

**2. Configure Slash Commands in Claude Code**

You need to copy the slash commands to your local Claude Code configuration:

```bash
# Create .claude directory in your main Code folder if it doesn't exist
mkdir -p ~/Desktop/Code/.claude

# Copy the slash commands
cp ~/session-knowledge-base/.claude/commands.md ~/Desktop/Code/.claude/commands.md
```

**Note**: The commands will work when running Claude Code from `~/Desktop/Code` or any subdirectory. Adjust the path based on where you keep your projects.

**3. Verify Setup**
```bash
# Check that files exist
ls -la ~/session-knowledge-base/
ls -la ~/Desktop/Code/.claude/

# Should see:
# ~/session-knowledge-base/KNOWLEDGE-BASE.md
# ~/session-knowledge-base/PROJECT-CHECKLIST.md
# ~/Desktop/Code/.claude/commands.md
```

**4. Configure Git (if not already done)**
```bash
# Set up git identity (use your GitHub email)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set up SSH key for GitHub (recommended) or use HTTPS token
# For SSH: https://docs.github.com/en/authentication/connecting-to-github-with-ssh
```

### Daily Usage

**Starting a New Project:**
1. Open terminal in your project directory (must be under `~/Desktop/Code/`)
2. Start Claude Code
3. Run `/project-init` to load knowledge
4. Follow the checklist and patterns
5. Build your project

**Ending a Session:**
1. Run `/summarize-session` to document learnings
2. Summary auto-saves and pushes to GitHub
3. Knowledge base automatically updated

### Troubleshooting

**Commands not found?**
- Ensure you're running Claude Code from `~/Desktop/Code` or a subdirectory
- Check `.claude/commands.md` exists in `~/Desktop/Code/.claude/`

**Git push fails?**
- Verify git credentials: `git config --list`
- Test push manually: `cd ~/session-knowledge-base && git push`
- Check SSH keys: `ssh -T git@github.com`

**Wrong file locations?**
- Knowledge base should be at: `~/session-knowledge-base/`
- Slash commands should be at: `~/Desktop/Code/.claude/commands.md`
- Session summaries save to: `~/Desktop/Code/session-summaries/`

---

## 📋 Quick Reference

### Essential Commands
```bash
# Start a new project
/project-init

# End a session (automatically checks if reviews are due)
/summarize-session

# Conduct knowledge base review
/knowledge-review

# Search knowledge base
grep -r "keyword" ~/session-knowledge-base/

# Browse past sessions
ls ~/session-knowledge-base/docs/sessions/

# Pull latest knowledge
cd ~/session-knowledge-base && git pull
```

### File Locations
- **Knowledge Base Repo**: `~/session-knowledge-base/`
- **Master Reference**: `~/session-knowledge-base/KNOWLEDGE-BASE.md`
- **Project Checklist**: `~/session-knowledge-base/PROJECT-CHECKLIST.md`
- **Slash Commands**: `~/Desktop/Code/.claude/commands.md`
- **Local Summaries**: `~/Desktop/Code/session-summaries/`

---

**Remember**: Every project makes this knowledge base smarter. Every mistake prevented is a win. 🎉
