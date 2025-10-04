# Project Initialization Checklist

**Last Updated**: 2025-10-03
**Purpose**: Standard checklist for starting new projects with accumulated best practices

---

## Pre-Project Setup

### Knowledge Review
- [ ] Run `/project-init` to load knowledge base
- [ ] Review KNOWLEDGE-BASE.md for relevant patterns
- [ ] Check `code-library/` for reusable components specific to project type
- [ ] Search `docs/sessions/` for similar past projects
- [ ] Review quality rules in `quality-rules/` if applicable

### Environment Preparation
- [ ] Verify Claude Code is running in correct directory
- [ ] Check `.claude/commands.md` exists and is configured
- [ ] Confirm git repository initialized (if needed)
- [ ] Verify GitHub remote configured (if using version control)
- [ ] Set up SSH keys or HTTPS tokens for git operations

### Project-Specific Considerations
- [ ] Identify project type (N8N, Integration, Frontend, Data Pipeline, etc.)
- [ ] Review type-specific guidelines in `docs/sessions/[project-type]/`
- [ ] Check for required tools/dependencies
- [ ] Verify API access or credentials if needed
- [ ] Review compliance requirements (A2A protocol, security, etc.)

---

## During Development

### Configuration Management
- [ ] Use absolute paths for cross-project consistency
- [ ] Document configuration scope (local vs global)
- [ ] Create `.gitignore` for sensitive files
- [ ] Set up environment variables properly
- [ ] Document any deviations from standard patterns

### Code Quality
- [ ] Reference code library before writing new solutions
- [ ] Follow established naming conventions
- [ ] Add inline documentation for complex logic
- [ ] Write reusable functions/components
- [ ] Consider error handling and edge cases

### Version Control
- [ ] Make atomic commits with clear messages
- [ ] Commit message format: "Action: specific change description"
- [ ] Push regularly to prevent data loss
- [ ] Branch appropriately (main for docs, feature branches for code)
- [ ] Add meaningful commit context

### N8N Workflow Projects (if applicable)
- [ ] Design workflow pattern (event-driven, scheduled, webhook, agentic)
- [ ] Plan error handling strategy upfront
- [ ] Consider state management approach
- [ ] Document node composition and purpose
- [ ] Plan testing strategy for workflows
- [ ] Consider MCP server integration for external services

### Agentic Systems (if applicable)
- [ ] Define context gathering strategy (SubAgents, compacting, search)
- [ ] Plan action taking approach (tools, MCP servers, scripts)
- [ ] Design output verification (quality rules, LLM judge, thresholds)
- [ ] Set loop iteration limits
- [ ] Build continuous improvement mechanism
- [ ] Ensure A2A protocol compliance if coordinating multiple agents

---

## Testing & Validation

### Quality Assurance
- [ ] Define success criteria upfront
- [ ] Create test cases for happy path
- [ ] Test edge cases and error scenarios
- [ ] Set up quality thresholds (if using LLM-as-a-Judge)
- [ ] Document validation approach

### Testing Checklist
- [ ] Unit tests for individual components
- [ ] Integration tests for end-to-end flows
- [ ] Load/performance testing if scalability matters
- [ ] Security review for sensitive operations
- [ ] User acceptance criteria met

---

## Documentation

### Required Documentation
- [ ] README.md with project overview
- [ ] Setup instructions for new developers
- [ ] API documentation (if applicable)
- [ ] Architecture diagrams for complex systems
- [ ] Runbook for operational procedures

### Knowledge Capture
- [ ] Document key decisions and rationale
- [ ] Note alternatives considered and trade-offs
- [ ] Record gotchas and how they were solved
- [ ] Extract reusable patterns for code library
- [ ] Update KNOWLEDGE-BASE.md with new learnings

---

## Session Closeout

### Documentation Finalization
- [ ] Run `/summarize-session` to create detailed summary
- [ ] Review auto-generated summary for completeness
- [ ] Ensure summary includes key learnings
- [ ] Verify git commit and push succeeded
- [ ] Check GitHub for successful upload

### Knowledge Base Updates
- [ ] Extract new patterns to code library
- [ ] Update KNOWLEDGE-BASE.md with new best practices
- [ ] Add gotchas to pitfalls section
- [ ] Document new tools or dependencies used
- [ ] Update project type guidelines if needed

### Handoff Preparation (if applicable)
- [ ] Team handoff notes documented
- [ ] Responsibilities clearly defined
- [ ] Training needs identified
- [ ] Access and credentials documented (securely)
- [ ] Contact information for questions

---

## Project-Type Specific Checklists

### N8N Workflow Projects
- [ ] N8N version documented
- [ ] Community nodes listed
- [ ] Credentials management approach defined
- [ ] Workflow exported and version controlled
- [ ] Execution settings configured
- [ ] Error notification setup
- [ ] Monitoring and alerting configured

### Integration Projects
- [ ] API endpoints documented
- [ ] Authentication method configured
- [ ] Rate limiting considered
- [ ] Error retry logic implemented
- [ ] Data transformation validated
- [ ] Webhook security verified (if applicable)

### Frontend Projects
- [ ] Component library decisions documented
- [ ] State management approach defined
- [ ] Routing configured
- [ ] API integration tested
- [ ] Responsive design verified
- [ ] Accessibility checked
- [ ] Performance optimized

### Data Pipeline Projects
- [ ] Data sources identified and accessible
- [ ] Transformation logic documented
- [ ] Data quality rules defined
- [ ] Pipeline monitoring setup
- [ ] Error handling for data issues
- [ ] Scalability considerations addressed
- [ ] Backup and recovery planned

### Analytics Projects
- [ ] Tableau/visualization tool configured
- [ ] Data source connections verified
- [ ] KPIs and metrics defined
- [ ] Dashboard design reviewed
- [ ] Refresh schedule configured
- [ ] Access controls set up
- [ ] Usage tracking enabled

### Agent Design Projects
- [ ] Agent autonomy level defined
- [ ] Human-in-loop strategy clear
- [ ] Decision points documented
- [ ] Tool access configured
- [ ] MCP servers integrated
- [ ] A2A protocol compliance verified
- [ ] Safety guardrails implemented

---

## Common Gotchas (Check These!)

### Configuration
- [ ] Verified `.claude/commands.md` is in correct scope
- [ ] Confirmed absolute paths used where needed
- [ ] Checked git repo exists before push operations
- [ ] Validated authentication configured for remote operations

### Git & Version Control
- [ ] Ensured not committing sensitive files (.env, credentials)
- [ ] Verified commit messages are descriptive
- [ ] Checked branch is up to date before push
- [ ] Confirmed remote tracking branch set up

### Performance
- [ ] Identified potential bottlenecks
- [ ] Considered scaling implications
- [ ] Optimized expensive operations
- [ ] Planned for increased load

### Security
- [ ] Reviewed data privacy requirements
- [ ] Implemented access controls
- [ ] Set up audit logging
- [ ] Secured credential management
- [ ] Validated input sanitization

---

## Quick Start Commands

```bash
# Initialize project
/project-init

# During development
git status                    # Check what's changed
git add .                     # Stage changes
git commit -m "message"      # Commit with message
git push                     # Push to remote

# End of session
/summarize-session           # Auto-generate and save summary
```

---

## Customization Guide

**Adapt this checklist for your project:**
1. Copy this checklist to your project directory
2. Remove irrelevant sections
3. Add project-specific items
4. Check off items as you complete them
5. Update master checklist with improvements

---

**Remember**: This checklist evolves with every project. If you find gaps, update it!
