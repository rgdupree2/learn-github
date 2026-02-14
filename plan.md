# GitHub Learning Plan

> Tailored for someone with Git/Bitbucket/Jenkins experience.
> Focus: GitHub-specific features and GitHub Actions.
> Pace: ~1 hr weekdays, a bit more on weekends.

---

## Phase 1: GitHub Core Features (Week 1-2)

These are the things GitHub does differently or better than Bitbucket.

### 1.1 Pull Requests & Code Review
- [ ] PR templates (`PULL_REQUEST_TEMPLATE.md`)
- [ ] Review process: requesting reviewers, required reviews, CODEOWNERS file
- [ ] Inline suggestions (suggest changes in review comments)
- [ ] Draft PRs
- [ ] Auto-merge and merge queue
- [ ] Branch protection rules and rulesets (newer replacement for branch protection)

### 1.2 Issues & Project Management
- [ ] GitHub Issues: labels, milestones, assignees
- [ ] Issue templates and issue forms (YAML-based)
- [ ] GitHub Projects (the newer board/table/roadmap views — not "classic" projects)
- [ ] Linking issues to PRs with keywords (`fixes #123`)
- [ ] Discussions (forum-style threads for a repo)

### 1.3 Repository Features
- [ ] GitHub Releases and tags (attaching binaries, changelogs)
- [ ] GitHub Packages (npm, Maven, Docker registry built into GitHub)
- [ ] GitHub Pages (static site hosting from a repo)
- [ ] Repository settings: visibility, features toggles, environments
- [ ] `.github` directory conventions (funding, templates, workflows)
- [ ] Dependabot for dependency updates and security alerts
- [ ] Code scanning and secret scanning (GitHub Advanced Security)

---

## Phase 2: GitHub Actions — Foundations (Week 3-4)

This is your Jenkins replacement. The mental model shift: pipelines are YAML files in `.github/workflows/`.

### 2.1 Core Concepts
- [ ] Workflow files: triggers, jobs, steps
- [ ] Events: `push`, `pull_request`, `schedule`, `workflow_dispatch` (manual), `repository_dispatch`
- [ ] Runners: GitHub-hosted vs self-hosted
- [ ] Expressions and contexts (`${{ github.ref }}`, `${{ secrets.MY_SECRET }}`)
- [ ] Environment variables and secrets management
- [ ] Job outputs and step outputs

### 2.2 Hands-On: Build Your First Workflows
- [ ] Simple CI: checkout, install deps, test, build
- [ ] Matrix builds (test across multiple OS/language versions)
- [ ] Caching dependencies (`actions/cache`)
- [ ] Uploading/downloading artifacts (`actions/upload-artifact`)
- [ ] Conditional execution (`if:` on jobs and steps)

---

## Phase 3: GitHub Actions — Intermediate (Week 5-6)

### 3.1 Reusable Patterns
- [ ] Reusable workflows (`workflow_call`)
- [ ] Composite actions (bundle multiple steps into one action)
- [ ] Using the GitHub Actions Marketplace
- [ ] Pinning actions to a SHA for security
- [ ] Concurrency control (cancel in-progress runs)

### 3.2 Deployment & Environments
- [ ] GitHub Environments (staging, production)
- [ ] Environment protection rules and required reviewers
- [ ] Deployment workflows with approval gates
- [ ] OIDC for cloud auth (keyless auth to AWS/Azure/GCP — no long-lived secrets)
- [ ] GitHub Container Registry (ghcr.io)

### 3.3 Practical Exercises
- [ ] Set up a CI pipeline for a real project (or sample project)
- [ ] Add a deployment step that deploys to GitHub Pages
- [ ] Create a scheduled workflow (e.g., dependency check, stale issue cleanup)
- [ ] Build a manual workflow with `workflow_dispatch` inputs

---

## Phase 4: GitHub Actions — Advanced (Week 7-8)

### 4.1 Writing Custom Actions
- [ ] JavaScript/TypeScript actions
- [ ] Docker container actions
- [ ] Action metadata (`action.yml`)
- [ ] Publishing actions to the Marketplace

### 4.2 Advanced Workflow Patterns
- [ ] Monorepo strategies: path filters, dynamic matrix
- [ ] Multi-job pipelines with dependencies (`needs:`)
- [ ] Status checks and required checks for PRs
- [ ] Working with the GitHub API from actions (`actions/github-script`)
- [ ] Workflow debugging and troubleshooting (`ACTIONS_STEP_DEBUG`)

---

## Phase 5: GitHub Ecosystem & Power Features (Week 9-10)

### 5.1 GitHub CLI (`gh`)
- [ ] Install and authenticate
- [ ] Create PRs, issues, releases from terminal
- [ ] Run and watch workflow runs from terminal
- [ ] Custom aliases and extensions

### 5.2 Security & Compliance
- [ ] Code scanning with CodeQL
- [ ] Secret scanning and push protection
- [ ] Dependency graph and Dependabot alerts
- [ ] Security policies (`SECURITY.md`)
- [ ] Audit log (for org-level)

### 5.3 Collaboration Features
- [ ] GitHub Copilot (AI-assisted coding)
- [ ] GitHub Codespaces (cloud dev environments)
- [ ] GitHub Apps vs OAuth Apps vs Personal Access Tokens
- [ ] Webhooks
- [ ] GitHub API (REST and GraphQL)

---

## Recommended Resources

### Free / Official
- [GitHub Skills](https://skills.github.com/) — interactive courses directly on GitHub
- [GitHub Actions docs](https://docs.github.com/en/actions) — the official reference
- [GitHub Blog](https://github.blog/) — new feature announcements

### O'Reilly (use your subscription)
- "Learning GitHub Actions" by Brent Laster (2023) — directly relevant, Actions-focused
- "GitHub For Dummies" — skip Git chapters, skim for GitHub-specific features
- Search for GitHub Actions video courses — some are Actions-only without Git padding

### Practice
- Create a personal repo specifically for experimenting with workflows
- Fork an open-source project and study their `.github/workflows/` directory
- Try contributing to a popular open-source project to experience GitHub's collaboration model firsthand

---

## Jenkins to GitHub Actions Mental Map

| Jenkins | GitHub Actions |
|---------|---------------|
| Jenkinsfile | `.github/workflows/*.yml` |
| Pipeline | Workflow |
| Stage | Job |
| Step | Step |
| Agent/Node | Runner |
| Credentials | Secrets / OIDC |
| Shared Libraries | Reusable workflows / Composite actions |
| Plugins | Actions (Marketplace) |
| Blue Ocean UI | Actions tab in repo |
| Multibranch Pipeline | Automatic (push/PR triggers) |

---

## Notes
- Adjust this plan as you go. Skip topics you pick up quickly, spend more time where needed.
- Each phase is roughly 2 weeks at ~1 hr/day, but move at your own pace.
- Check items off as you complete them.