# Azure-Stack-HCI-Workshop — Claude Code Context

## What this repo is

Azure Stack HCI is a hyperconverged infrastructure (HCI) cluster solution that hosts virtualized Windows and Linux workloads and their storage in a hybrid environment that combines on-premises infrastructure with cloud services. Azure hybrid services enhance the cluster with capabilities such as cloud-based monitoring, Site Recovery, and virtual machine (VM) backups, as well as a central view of all of your Azure Stack HCI deployments in the Azure portal. You can manage the cluster with your ...

---

## ADO project details

- **ADO org:** https://dev.azure.com/hybridcloudsolutions
- **ADO project:** Platform Engineering
- **Area path:** Platform Engineering\Onboarding
- **Work item format:** `AB#<id>` in commit messages and PR descriptions

---

## Standards

This repo follows all HCS platform standards defined in the Platform Engineering repo:

| Standard | Reference |
|---|---|
| Governance | [docs/standards/governance.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/governance.md) |
| Scripting (PowerShell 7) | [docs/standards/scripting.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/scripting.md) |
| Automation | [docs/standards/automation.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/automation.md) |
| Variables and naming | [docs/standards/variables.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/variables.md) |
| Documentation | [docs/standards/documentation.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/documentation.md) |
| Claude Code | [docs/standards/claude-code.md](https://dev.azure.com/hybridcloudsolutions/Platform%20Engineering/_git/Platform%20Engineering?path=/docs/standards/claude-code.md) |

Key rules:
- All scripts: PowerShell 7+ only. `#Requires -Version 7.0`, `Set-StrictMode -Version Latest`, ` $ErrorActionPreference = 'Stop'`.
- All docs: Markdown only. No Word documents in any repo.
- Commit format: `type(scope): short description` — types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`
- No secrets, tokens, or credentials committed to any file.

---

## Key facts

| Fact | Value |
|---|---|
| Primary language | Mixed |
| GitHub org | kristopherjturner |
| Azure login | kris@hybridsolutions.cloud |
| Key Vault | kv-hcs-vault-01 |

### Environment variables expected

| Variable | Source | Purpose |
|---|---|---|
| `GITHUB_TOKEN` | kv-hcs-vault-01 via Load-HCSEnvironment.ps1 | GitHub CLI and git operations |
| `AZURE_DEVOPS_EXT_PAT` | kv-hcs-vault-01 via Load-HCSEnvironment.ps1 | ADO CLI (`az boards`, `az devops`) |
Load before starting a session:
```powershell
. E:\git\platform\scripts\Load-HCSEnvironment.ps1
```

### Build and test commands

```
# No standard build commands detected
```

---

## Repo structure

```
Azure-Stack-HCI-Workshop/
├── .claude/
    └── settings.json
├── CIP Manifest/
    └── readme.md
├── Datasheet/
    ├── Unapproved/
    ├── Azure Stack HCI Workshop Datasheet_with OptionalAddons.pdf
    └── readme.md
├── Delivery Guide/
    ├── Azure_Stack_HCI_AKS_Delivery_Guide.md
    ├── Azure_Stack_HCI_Chalk_and_Talk.md
    ├── Azure_Stack_HCI_Compute_delivery_guide.md
    ├── Azure_Stack_HCI_Core_Networking_delivery_guide.md
    └── Azure_Stack_HCI_Full_delivery_guide.md
├── DemoFiles/
    └── readme.md
├── Demos/
    └── readme.md
├── LabFiles/
    └── readme.md
├── Labs/
    └── readme.md
├── old/
    ├── Datasheet_ASHCI_With_AKS.pptx
    ├── Datasheet_ASHCI_With_SDN.pptx
    ├── Datasheet_ASHCI.pptx
    └── readme.md
├── PowerPoint/
    ├── _ChalkTalk/
    ├── 00_Intro/
    ├── 01_Management/
    ├── 02_Compute/
    └── 03_Storage/
├── Wiki/
    └── readme.md
├── .gitattributes
├── CLAUDE.md
└── README.md
```

---

## Claude Code actions

**Run autonomously:**
- Read, search, and grep any file in this repo
- Write and edit files in this repo
- `git add`, `git commit`, `git push`
- `gh issue`, `gh pr`, `gh run` CLI commands


**Always confirm before:**
- Creating or deleting Azure resources
- Any `az` CLI write operation that modifies Azure state
- Running destructive operations
- Making API calls to external services


---

## Subagents available in this repo

- `Azure-Stack-HCI-Workshop-engineer` (model: sonnet) — Expert in `Azure-Stack-HCI-Workshop`: deep knowledge of this repo's structure, conventions, and development workflow.

User-level agents (available in every repo session): `triage-lookup`, `markdown-prose-editor`, `azurelocal-domain-expert`, `mkdocs-material-doctor`, `turner-module-scaffold-engineer`, `mms-2026-demo-presenter`.

---

## Owner

**Kristopher Turner**
kris@hybridsolutions.cloud
Senior Product Technology Architect, TierPoint | Microsoft MVP (Azure) | MCT
Owner, Hybrid Cloud Solutions LLC — hybridsolutions.cloud
Country Cloud Boy — thisismydemo.cloud