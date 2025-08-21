# Universal BRTOPS Project Structure Template

## Complete Project Directory Structure

```
project-root/
├── docs/
│   ├── 00_project/
│   │   ├── BRTOPS.md                # Project-specific BRTOPS configuration
│   │   ├── README.md                # Project overview and getting started
│   │   ├── structure-guide.md       # Folder structure explanation
│   │   └── team-guide.md           # Team collaboration guidelines
│   ├── 01_architecture/
│   │   ├── system-design.md         # High-level system architecture
│   │   ├── decision-records/        # Architecture Decision Records (ADRs)
│   │   │   ├── ADR-001-example.md
│   │   │   └── template.md
│   │   ├── diagrams/               # Architecture diagrams and visuals
│   │   │   ├── system-overview.md
│   │   │   └── data-flow.md
│   │   └── technology-stack.md     # Technology choices and rationale
│   ├── 02_features/
│   │   ├── {feature-name}/         # Feature-specific 6-folder structure
│   │   │   ├── 1-requirements/
│   │   │   │   ├── requirements.md
│   │   │   │   ├── user-stories.md
│   │   │   │   └── acceptance-criteria.md
│   │   │   ├── 2-analysis/
│   │   │   │   ├── risk-assessment.md
│   │   │   │   ├── feasibility-study.md
│   │   │   │   └── impact-analysis.md
│   │   │   ├── 3-architecture/
│   │   │   │   ├── design-overview.md
│   │   │   │   ├── technical-design.md
│   │   │   │   └── integration-points.md
│   │   │   ├── 4-development/
│   │   │   │   ├── implementation-log.md
│   │   │   │   ├── code-decisions.md
│   │   │   │   └── testing-notes.md
│   │   │   ├── 5-debugging/
│   │   │   │   ├── issues-log.md
│   │   │   │   ├── solutions.md
│   │   │   │   └── troubleshooting.md
│   │   │   └── 6-key_learnings/
│   │   │       ├── lessons-learned.md
│   │   │       ├── best-practices.md
│   │   │       └── future-improvements.md
│   │   └── feature-index.md        # Master list of all features
│   ├── 03_operations/
│   │   ├── deployment/             # Deployment procedures and scripts
│   │   │   ├── deployment-guide.md
│   │   │   ├── environment-setup.md
│   │   │   └── rollback-procedures.md
│   │   ├── monitoring/             # System monitoring and alerting
│   │   │   ├── monitoring-setup.md
│   │   │   ├── alert-definitions.md
│   │   │   └── dashboard-configs.md
│   │   └── maintenance/            # System maintenance procedures
│   │       ├── backup-procedures.md
│   │       ├── update-procedures.md
│   │       └── troubleshooting.md
│   ├── 04_after-action-reports/    # Post-completion analysis and retrospectives
│   │   ├── features/               # Feature completion AARs
│   │   │   └── feature-aar-template.md
│   │   ├── projects/               # Project milestone AARs
│   │   │   └── project-aar-template.md
│   │   └── operations/             # Operational incident AARs
│   │       └── incident-aar-template.md
│   ├── 05_quality/
│   │   ├── testing/                # Testing strategies and procedures
│   │   │   ├── testing-strategy.md
│   │   │   ├── test-cases.md
│   │   │   └── automation-setup.md
│   │   ├── quality-gates/          # Quality assurance gate definitions
│   │   │   ├── sev-0-gates.md
│   │   │   ├── sev-1-gates.md
│   │   │   ├── sev-2-gates.md
│   │   │   └── gate-automation.md
│   │   └── reviews/                # Code review guidelines and checklists
│   │       ├── review-guidelines.md
│   │       ├── security-checklist.md
│   │       └── performance-checklist.md
│   ├── 06_for-agents/             # AI agent-specific documentation
│   │   ├── brtops-integration.md   # BRTOPS framework integration
│   │   ├── project-context.md      # Project-specific AI context
│   │   └── workflow-automation.md  # Automated workflow definitions
│   └── 07_archive/
│       ├── completed-features/     # Archived completed feature documentation
│       ├── deprecated/             # Deprecated documentation and decisions
│       ├── migrations/             # Migration records and procedures
│       └── historical/             # Historical project information
├── .brtops/
│   ├── config.json                 # BRTOPS project configuration
│   ├── feature-registry.json       # Active and completed features registry
│   ├── templates/                  # Project-specific templates
│   │   ├── feature-template.md     # Feature documentation template
│   │   ├── commit-template.md      # Git commit message template
│   │   ├── pr-template.md          # Pull request template
│   │   └── adr-template.md         # Architecture Decision Record template
│   ├── hooks/                      # Git hooks for BRTOPS integration
│   │   ├── pre-commit              # Pre-commit validation
│   │   ├── commit-msg              # Commit message validation
│   │   ├── pre-push                # Pre-push quality gates
│   │   └── post-merge              # Post-merge automation
│   └── quality-gates/              # Quality gate definitions and scripts
│       ├── coverage-gates.json     # Test coverage requirements
│       ├── security-gates.json     # Security validation requirements
│       └── performance-gates.json  # Performance benchmark requirements
├── .gitignore                      # Git ignore patterns
├── .github/                        # GitHub-specific configuration (if applicable)
│   ├── workflows/                  # CI/CD workflow definitions
│   ├── ISSUE_TEMPLATE/            # Issue templates
│   ├── PULL_REQUEST_TEMPLATE.md   # Pull request template
│   └── CODEOWNERS                 # Code ownership definitions
└── README.md                       # Project root README
```

## Folder Purpose Definitions

### `/docs/00_project/`
**Purpose**: Core project documentation and configuration
- **BRTOPS.md**: Project-specific BRTOPS settings and overrides
- **README.md**: Project overview, setup instructions, team onboarding
- **structure-guide.md**: Explanation of folder structure and conventions
- **team-guide.md**: Team collaboration guidelines and processes

### `/docs/01_architecture/`
**Purpose**: High-level system design and architectural decisions
- **system-design.md**: Overall system architecture and design principles
- **decision-records/**: Architecture Decision Records (ADRs) for major decisions
- **diagrams/**: Visual representations of system architecture
- **technology-stack.md**: Technology choices and rationale

### `/docs/02_features/`
**Purpose**: Feature-specific documentation using enhanced 6-folder structure (v1.1.003)
- Each feature gets its own folder with standardized enhanced structure
- **feature-index.md**: Master registry of all features and their status
- Follows BRTOPS phase-based documentation lifecycle

#### Enhanced 6-Folder Structure Requirements
- **01-objectives/**: Requirements, context, and constraints (ALL files REQUIRED)
- **02-analysis/**: Risk assessment and technical analysis (ALL files REQUIRED)
- **03-architecture-design/**: System design and architecture decisions (ALL files REQUIRED)
- **04-development/**: Implementation tracking and logs (ALL files REQUIRED)
- **05-debugging/**: Troubleshooting and issue resolution (REQUIRED for SEV-0/SEV-1)
- **06-key_learnings/**: Knowledge capture and future reference (ALL files REQUIRED)

### `/docs/03_operations/`
**Purpose**: Operational procedures and system management
- **deployment/**: How to deploy and manage deployments
- **monitoring/**: System monitoring, alerting, and observability
- **maintenance/**: Ongoing system maintenance and procedures

### `/docs/04_after-action-reports/`
**Purpose**: Post-completion analysis and retrospectives (DEBRIEF outputs)
- **features/**: After Action Reports for completed features
- **projects/**: After Action Reports for project milestones
- **operations/**: After Action Reports for operational incidents
- **Format**: Standard BRTOPS AAR template with lessons learned and recommendations

### `/docs/05_quality/`
**Purpose**: Quality assurance standards and procedures
- **testing/**: Testing strategies, test cases, and automation
- **quality-gates/**: SEV-based quality gate definitions
- **reviews/**: Code review guidelines and checklists

### `/docs/06_for-agents/`
**Purpose**: AI agent-specific documentation and context
- **brtops-integration.md**: How BRTOPS is configured for this project
- **project-context.md**: Project-specific context for AI agents
- **workflow-automation.md**: Automated workflow definitions

### `/docs/07_archive/`
**Purpose**: Historical and archived documentation
- **completed-features/**: Documentation for completed features
- **deprecated/**: Deprecated decisions and documentation
- **migrations/**: Records of major system migrations
- **historical/**: Historical project information

### `/.brtops/`
**Purpose**: BRTOPS framework configuration and automation
- **config.json**: Project-specific BRTOPS configuration
- **feature-registry.json**: Registry of features and their lifecycle status
- **templates/**: Project-specific document templates
- **hooks/**: Git hooks for BRTOPS workflow automation
- **quality-gates/**: Automated quality gate definitions

## Usage Instructions

### Creating New Project
```bash
INIT PROJECT [TYPE] SEV-[X] [project-name]
# Creates complete structure above
# Initializes git repository
# Sets up BRTOPS configuration
# Creates initial documentation
```

### Adding New Feature
```bash
INIT FEATURE SEV-[X] [feature-name]
# Creates 6-folder structure in docs/02_features/
# Updates feature registry
# Creates feature branch
# Sets up documentation templates
```

### Maintaining Structure
```bash
CHECK STRUCTURE
# Validates complete structure compliance
# Reports missing folders or files
# Suggests structure improvements

VALIDATE MIGRATION
# After migrating existing project
# Ensures all required elements present
```

This structure provides complete project organization while maintaining flexibility for different project types and scales.