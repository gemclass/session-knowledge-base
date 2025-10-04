# Knowledge Base - Master Reference

**Last Updated**: 2025-10-03
**Purpose**: Living document of accumulated learnings, best practices, and guidelines from all projects

---

## Table of Contents
1. [Core Principles](#core-principles)
2. [Best Practices](#best-practices)
3. [Common Pitfalls & How to Avoid](#common-pitfalls--how-to-avoid)
4. [Decision Frameworks](#decision-frameworks)
5. [Preferred Approaches](#preferred-approaches)
6. [Tool & Technology Guidelines](#tool--technology-guidelines)

---

## Core Principles

### Configuration Management
- **Use absolute paths for cross-project consistency** - Relative paths only work in specific contexts
- **Centralize configuration when possible** - Makes maintenance easier across multiple projects
- **Document scope and limitations** - Be explicit about where configs apply

### Automation & Workflows
- **Automate repetitive tasks** - If you do it twice, automate it
- **Build in version control from the start** - Don't treat it as an afterthought
- **Dual storage for important data** - Local + remote for redundancy

### Knowledge Capture
- **Document as you go, not after** - Context is lost quickly
- **Extract patterns, not just solutions** - Look for reusable approaches
- **Track what doesn't work too** - Failed approaches save future time

---

## Best Practices

### Claude Code Configuration
- **Slash commands are directory-specific** - Place `.claude/commands.md` in appropriate scope
- **Use absolute paths in slash commands** - Ensures consistent behavior across projects
- **Include auto-save in documentation commands** - Prevents loss of valuable context

### Git Workflows
- **Standardize commit messages** - Use consistent format across projects
- **Auto-push documentation** - Reduces friction in knowledge sharing
- **Separate detailed logs from summaries** - Keep both for different use cases

### Project Setup
- **Start with knowledge review** - Load existing patterns before coding
- **Create project-specific checklists** - Adapt master checklist to context
- **Document deviations from standards** - Explain why when breaking patterns

---

## Common Pitfalls & How to Avoid

### Configuration Issues
**Pitfall**: Assuming configuration applies globally when it's directory-specific
- **Why it happens**: `.claude/` folder scope not clearly understood
- **How to avoid**: Always verify config file location and test from different directories
- **Solution**: Use absolute paths and document scope limitations

**Pitfall**: Forgetting to push documentation changes to remote
- **Why it happens**: Manual git workflow prone to human error
- **How to avoid**: Automate git operations in slash commands
- **Solution**: Build commit & push into documentation workflow

### Git & Version Control
**Pitfall**: Not verifying git repo exists before pushing
- **Why it happens**: Assuming repo is cloned and accessible
- **How to avoid**: Add validation checks before git operations
- **Solution**: Check repo path exists, prompt user if not found

**Pitfall**: Authentication failures on push
- **Why it happens**: Git credentials not configured
- **How to avoid**: Document prerequisites in setup checklist
- **Solution**: Verify SSH keys or HTTPS tokens before first use

---

## Decision Frameworks

### When to Automate
**Consider automation when**:
- Task performed more than twice
- Manual process prone to errors
- Time savings > setup cost
- Consistency is critical

**Skip automation when**:
- One-time task
- High complexity, low frequency
- Automation adds more friction than value

### Configuration Scope Selection
**Use local (project-specific) config when**:
- Project has unique requirements
- Testing new approaches
- Temporary overrides needed

**Use global config when**:
- Standard across all projects
- Cross-project tools
- Personal preferences/defaults

### Storage Location Strategy
**Local only**:
- Temporary files
- Build artifacts
- Personal scratch work

**Local + Remote**:
- Important documentation
- Knowledge base content
- Reusable code patterns

**Remote only**:
- Shared team resources
- Production configurations
- Published artifacts

---

## Preferred Approaches

### Documentation
- **Format**: Markdown for all documentation
- **Structure**: Clear hierarchy with TOC for long docs
- **Metadata**: Always include date, author, project context
- **Code examples**: Include language tags and comments

### File Naming
- **Pattern**: `YYYY-MM-DD-project-name-description.md`
- **Rationale**: Chronological + context prevents collisions
- **Example**: `2025-10-03-session-knowledge-base-summary.md`

### Knowledge Organization
- **By type**: Separate code, docs, configs
- **By project type**: N8N, integration, frontend, etc.
- **By language**: Python, JavaScript, Bash
- **Master files**: Living documents that synthesize learnings

---

## Tool & Technology Guidelines

### Claude Code
- **Version**: Latest stable
- **Key features used**: Slash commands, local configuration
- **Custom commands**: `/summarize-session`, `/project-init`
- **Best use cases**: Automated documentation, knowledge capture

### Git & GitHub
- **Workflow**: Feature branch → PR → main (for code)
- **Workflow**: Direct to main for documentation
- **Commit format**: Descriptive messages with context
- **Repository structure**: Organized by type and project

### N8N (when applicable)
- **Use for**: Workflow automation, agent orchestration
- **Pattern library**: See `code-library/n8n/`
- **Best practices**: Error handling, state management
- **Community nodes**: Document custom installations

---

## Evolution Guidelines

### Updating This Document
1. Add new learnings immediately after session (`/summarize-session` does this automatically)
2. Extract patterns, don't just list facts
3. Keep sections concise - link to detailed docs
4. Conduct scheduled reviews to keep content fresh
5. Archive deprecated approaches to "Archive" section at bottom

### Scheduled Reviews

**Review tracking**: `.review-tracker.json` stores last review dates

**Weekly Review** (Every 7 days, ~5-10 min):
- Quick scan of recent sessions for critical learnings
- Extract immediate patterns to knowledge base
- Update best practices if needed
- Run `/knowledge-review` when prompted

**Monthly Review** (Every 30 days, ~15-30 min):
- Review all sessions from past month
- Consolidate duplicate patterns
- Update code library with new patterns
- Verify links and references
- Update PROJECT-CHECKLIST.md

**Quarterly Review** (Every 90 days, ~1-2 hours):
- Comprehensive audit of entire knowledge base
- Archive outdated approaches
- Restructure sections if needed
- Major code library updates
- Review quality standards
- Plan improvements for next quarter

**Automated Reminders**:
- `/summarize-session` checks review dates automatically
- Prompts you when reviews are overdue
- Run `/knowledge-review` to conduct review and update tracking

### Quality Standards
- **Actionable**: Every item should guide decisions
- **Specific**: Avoid vague generalities
- **Tested**: Only include proven approaches
- **Maintained**: Remove or update stale content via scheduled reviews

---

## Quick Reference

### Starting a New Project
1. Run `/project-init` to load this knowledge base
2. Review relevant code library patterns
3. Check project-type-specific guidelines
4. Create project checklist from master template

### Ending a Session
1. Run `/summarize-session` to document learnings
2. Extract key insights to this master document
3. Update code library with new patterns
4. Commit all changes to GitHub

### When Stuck
1. Search this knowledge base for similar patterns
2. Check `docs/sessions/` for related project examples
3. Review `code-library/` for reusable solutions
4. Document new solution for future reference

---

**Remember**: This is a living document. Every project makes it smarter. Every mistake prevented is a win.
