 PickBetta Git Flow Guide
🛠️ Main Branches
main: production releases only
staging: QA & integration testing
dev: active development
🌱 Support Branches
feature/*: new features
bugfix/*: fixes during development
hotfix/*: urgent production fixes
✅ 1. Setup Git Flow
🧩 macOS / Linux
Install Git Flow globally:

brew install git-flow     # macOS
sudo apt install git-flow # Linux
🪟 Windows
Option 1: Git Bash (Recommended)
Download and install Git for Windows
Open Git Bash (not CMD or PowerShell)
Run the install script:
curl -L https://raw.githubusercontent.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh | bash
Verify installation:
git flow version
Option 2: Chocolatey (If installed)
choco install git-flow-avh
Option 3: WSL (Ubuntu)
sudo apt install git-flow
🚀 Initialize Git Flow in your project:
git flow init
Use the following settings:

Production: main
Development: dev
Prefixes:
Feature: feature/
Bugfix: bugfix/
Hotfix: hotfix/
Release: release/
🧪 2. Create a New Feature
git flow feature start user-authentication
Creates feature/user-authentication from dev

💾 3. Commit Your Changes
git add .
git commit -m "feat: add login route and JWT handler"
Commit prefixes:

feat: – new feature
fix: – bug fix
chore: – maintenance
docs: – documentation
refactor: – code restructure
test: – tests added or changed
🔁 4. Finish Feature Branch
git flow feature finish user-authentication
⚠️ This merges your feature into local dev only. You still need to push dev manually.

git push origin dev  # Only if PR has already been merged!
🛠️ 5. Bug Fixes
git flow bugfix start api-token-bug
# make your fix
git commit -m "fix: correct token validation logic"
git flow bugfix finish api-token-bug
Always push and create PR before finishing the branch.

🔥 6. Hotfixes (Production)
git flow hotfix start urgent-login-fix
# fix the issue
git commit -m "hotfix: fix production login crash"
git flow hotfix finish urgent-login-fix
This merges into main and dev

git push origin main
git push origin dev
🔀 7. Pull Requests (Code Review)
git push origin feature/user-authentication
Then, create a PR on GitHub:

Base: dev (or staging)
Compare: feature/your-branch
Title: feat: add user authentication
Add reviewers & description
⚙️ Optional: Create PR from CLI (if GitHub CLI is installed)
gh pr create --base dev --head feature/user-authentication --title "feat: add user authentication" --body "Implemented JWT-based login and route protection."
GitHub CLI: https://cli.github.com

🌿 8. Release Branch (Optional)
git flow release start v1.1.0
# finalize, polish, test
git flow release finish v1.1.0
git push origin main
git push origin staging
📌 Quick Summary
Task	Command
Start feature	git flow feature start <name>
Finish feature	git flow feature finish <name>
Start bugfix	git flow bugfix start <name>
Finish bugfix	git flow bugfix finish <name>
Start hotfix	git flow hotfix start <name>
Finish hotfix	git flow hotfix finish <name>
Push branch	git push origin <branch>
Sync dev	git pull origin dev
PR from CLI	gh pr create --base dev --head <branch> --title "..." --body "..."
✅ Git Flow Do’s & Don’ts
✅ Do:
✅ Use git flow feature start for every new task
✅ Commit early and often
✅ Push your feature branch: git push origin feature/your-task
✅ Open a PR to dev for review
✅ Merge to dev only through PRs
✅ Run git pull origin dev before starting a new branch
❌ Don’t:
❌ Push directly to dev, staging, or main
❌ Run git flow feature finish before your PR is reviewed and merged
❌ Merge unreviewed changes
❌ Use shared branches (dev, main) for experimental work
This guide keeps our workflow clean, fast, and collaborative. Make sure to always branch from the right base and submit PRs for review.

Let’s build smart. Let’s PickBetta.

TEAM
Stanley agu.chux@pickbetta.com