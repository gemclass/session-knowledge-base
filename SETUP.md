# Setup Guide - Session Knowledge Base

**Quick setup guide for team members to get the knowledge base system running locally.**

---

## Prerequisites

- [ ] Claude Code CLI installed and working
- [ ] Git installed (`git --version` to verify)
- [ ] GitHub account with access to `gemclass/session-knowledge-base` repo
- [ ] Terminal access (Mac/Linux)

---

## Step-by-Step Setup

### 1. Clone the Knowledge Base Repository

```bash
# Navigate to home directory
cd ~

# Clone the repository
git clone https://github.com/gemclass/session-knowledge-base.git

# Verify it worked
ls ~/session-knowledge-base/
# You should see: KNOWLEDGE-BASE.md, PROJECT-CHECKLIST.md, README.md, code-library/, docs/, etc.
```

### 2. Set Up Your Code Directory Structure

The slash commands are configured to work from a specific directory structure. You have two options:

#### Option A: Use Standard Location (Recommended)
```bash
# Create the Code directory on Desktop if it doesn't exist
mkdir -p ~/Desktop/Code

# This is where you'll run Claude Code from
cd ~/Desktop/Code
```

#### Option B: Customize for Your Setup
If you keep your code elsewhere, you'll need to:
1. Update paths in `~/session-knowledge-base/.claude/commands.md`
2. Change `~/Desktop/Code` to your preferred location throughout the file

### 3. Configure Slash Commands

```bash
# Create .claude directory in your Code folder
mkdir -p ~/Desktop/Code/.claude

# Copy the slash commands configuration
cp ~/session-knowledge-base/.claude/commands.md ~/Desktop/Code/.claude/commands.md

# Verify the file exists
cat ~/Desktop/Code/.claude/commands.md | head -20
# You should see the /summarize-session command
```

### 4. Configure Git Credentials

#### Set Your Git Identity
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

#### Set Up GitHub Authentication

**Option A: SSH Key (Recommended)**
```bash
# Check if you have an SSH key
ls -la ~/.ssh/id_*.pub

# If no key exists, create one
ssh-keygen -t ed25519 -C "your.email@example.com"

# Copy your public key
cat ~/.ssh/id_ed25519.pub
# Copy the output and add to GitHub: https://github.com/settings/keys

# Test the connection
ssh -T git@github.com
# Should say: "Hi username! You've successfully authenticated..."
```

**Option B: HTTPS Token**
```bash
# Create a Personal Access Token on GitHub
# Go to: https://github.com/settings/tokens
# Click "Generate new token (classic)"
# Select scopes: repo (all), workflow
# Copy the token and save it securely

# Git will prompt for credentials on first push
# Username: your-github-username
# Password: paste-your-token-here
```

### 5. Create Local Summaries Directory

```bash
# This directory will store local copies of your session summaries
mkdir -p ~/Desktop/Code/session-summaries
```

### 6. Verify Complete Setup

Run these verification commands:

```bash
# 1. Check knowledge base repo exists
ls ~/session-knowledge-base/KNOWLEDGE-BASE.md
# Should show: /Users/yourname/session-knowledge-base/KNOWLEDGE-BASE.md

# 2. Check slash commands are configured
ls ~/Desktop/Code/.claude/commands.md
# Should show: /Users/yourname/Desktop/Code/.claude/commands.md

# 3. Check local summaries directory exists
ls ~/Desktop/Code/session-summaries/
# Should show empty directory or existing summaries

# 4. Test git push access
cd ~/session-knowledge-base
git pull
# Should say: Already up to date (or pull latest changes)
```

---

## Testing the System

### Test /project-init Command

```bash
# Navigate to your Code directory
cd ~/Desktop/Code

# Start Claude Code
claude

# In Claude Code, run:
/project-init

# You should see the knowledge base content load
```

### Test /summarize-session Command

```bash
# In Claude Code, run:
/summarize-session

# Follow the prompts to create a test summary
# Verify it appears in:
# - ~/Desktop/Code/session-summaries/
# - ~/session-knowledge-base/docs/sessions/
# - GitHub repository (check online)
```

---

## Common Issues & Solutions

### Issue: Slash commands not found

**Problem**: When you type `/project-init` or `/summarize-session`, Claude Code says command not found.

**Solutions**:
1. Verify you're in the right directory:
   ```bash
   pwd
   # Should show: /Users/yourname/Desktop/Code or a subdirectory
   ```

2. Check slash commands file exists:
   ```bash
   ls ~/Desktop/Code/.claude/commands.md
   ```

3. Restart Claude Code after adding commands

### Issue: Git push fails with "permission denied"

**Problem**: `/summarize-session` creates summary but fails to push to GitHub.

**Solutions**:
1. Check SSH key is added to GitHub:
   ```bash
   ssh -T git@github.com
   ```

2. Or switch to HTTPS and use token:
   ```bash
   cd ~/session-knowledge-base
   git remote set-url origin https://github.com/gemclass/session-knowledge-base.git
   ```

3. Test push manually:
   ```bash
   cd ~/session-knowledge-base
   git pull
   git push
   ```

### Issue: Files saving to wrong location

**Problem**: Summaries not appearing in expected directories.

**Solutions**:
1. Check your current working directory:
   ```bash
   pwd
   ```

2. Ensure you're running from `~/Desktop/Code` or subdirectory

3. Verify paths in commands:
   ```bash
   cat ~/Desktop/Code/.claude/commands.md | grep "session-summaries"
   ```

### Issue: Knowledge base repo not found

**Problem**: Commands reference `~/session-knowledge-base` but it doesn't exist.

**Solution**:
```bash
# Clone the repo if missing
cd ~
git clone https://github.com/gemclass/session-knowledge-base.git
```

---

## Directory Structure Reference

After complete setup, your system should look like this:

```
~/Desktop/Code/
├── .claude/
│   └── commands.md                 # Slash commands configuration
├── session-summaries/              # Local copies of summaries
│   └── [YYYY-MM-DD-project-summary.md files]
└── [your-various-projects]/        # Your actual code projects

~/session-knowledge-base/           # The knowledge base repo
├── .claude/
│   └── commands.md                 # Source slash commands
├── KNOWLEDGE-BASE.md               # Master reference
├── PROJECT-CHECKLIST.md            # Project checklist
├── README.md                       # Documentation
├── SETUP.md                        # This file
├── code-library/                   # Reusable code patterns
│   ├── bash/
│   ├── javascript/
│   ├── n8n/
│   └── python/
├── docs/
│   ├── patterns/
│   └── sessions/                   # All session summaries
│       ├── n8n-workflow/
│       ├── integration/
│       ├── frontend/
│       ├── data-pipeline/
│       ├── analytics/
│       ├── agent-design/
│       ├── a2a-protocol/
│       └── other/
├── mcp-servers/
└── quality-rules/
```

---

## Daily Workflow

### Starting a New Project
```bash
cd ~/Desktop/Code/my-new-project
claude
# In Claude: /project-init
```

### Ending a Session
```bash
# In Claude: /summarize-session
# Automatically saves locally and pushes to GitHub
```

### Syncing Latest Knowledge
```bash
cd ~/session-knowledge-base
git pull
# Get latest learnings from team
```

---

## Getting Help

### Documentation
- **Full Documentation**: See [README.md](./README.md)
- **Knowledge Base**: See [KNOWLEDGE-BASE.md](./KNOWLEDGE-BASE.md)
- **Project Checklist**: See [PROJECT-CHECKLIST.md](./PROJECT-CHECKLIST.md)

### Quick Reference
```bash
# View available slash commands
cat ~/Desktop/Code/.claude/commands.md

# Search knowledge base
grep -r "keyword" ~/session-knowledge-base/

# List all past sessions
ls ~/session-knowledge-base/docs/sessions/

# Pull latest knowledge
cd ~/session-knowledge-base && git pull
```

### Team Communication
- Open an issue on GitHub for problems or questions
- Check existing session summaries for examples
- Review KNOWLEDGE-BASE.md for solutions to common issues

---

## Next Steps

1. ✅ Complete setup steps above
2. ✅ Run verification commands
3. ✅ Test both `/project-init` and `/summarize-session`
4. ✅ Review [KNOWLEDGE-BASE.md](./KNOWLEDGE-BASE.md) to understand accumulated learnings
5. ✅ Read [PROJECT-CHECKLIST.md](./PROJECT-CHECKLIST.md) for best practices
6. ✅ Start using the system on your next project!

---

**Questions?** Check the troubleshooting section above or ask on the team chat!
