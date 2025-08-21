# BRTOPS Git Workflow Integration

## Branch Naming Conventions

### Feature Development Branches
```bash
# Standard Pattern
feature/sev-{X}-{feature-name}

# Examples
feature/sev-0-user-authentication    # Critical: User authentication system
feature/sev-1-payment-processing     # High: Payment processing integration  
feature/sev-2-dashboard-ui          # Moderate: User dashboard interface
feature/sev-3-button-styling        # Low: UI button style improvements
feature/sev-4-icon-updates          # Minimal: Icon asset updates
feature/sev-5-typo-fixes            # Trivial: Documentation typo fixes
```

### Documentation Branches
```bash
# Documentation-only changes
docs/sev-{X}-{change-description}

# Examples  
docs/sev-2-api-documentation        # API documentation update
docs/sev-3-user-guide-improvement   # User guide enhancements
docs/sev-5-readme-updates           # README file updates
```

### Hotfix Branches
```bash
# Emergency fixes
hotfix/sev-{X}-{issue-description}

# Examples
hotfix/sev-0-security-vulnerability  # Critical security patch
hotfix/sev-1-data-corruption-fix     # High priority data fix
hotfix/sev-2-login-issue-fix         # Moderate priority login fix
```

### Maintenance Branches
```bash
# Maintenance and cleanup work
maint/{maintenance-type}

# Examples
maint/dependency-updates            # Dependency version updates
maint/code-cleanup                  # Code refactoring and cleanup
maint/performance-optimization      # Performance improvements
maint/security-updates              # Security-related maintenance
```

### Release Branches
```bash
# Release preparation
release/v{major}.{minor}.{patch}

# Examples
release/v1.2.0                      # Major feature release
release/v1.1.3                      # Patch release
release/v2.0.0                      # Major version release
```

## Phase-Based Commit Templates

### GO RCC Phase Commits
```bash
🎯 GO RCC: {feature-name} - Requirements collection

Brief description of what requirements were gathered.

## Requirements Collected
- [ ] User requirements and user stories
- [ ] Acceptance criteria defined
- [ ] Technical constraints identified  
- [ ] Success metrics established
- [ ] Risk assessment completed

## Stakeholders Consulted
- {List of stakeholders involved}

## Next Phase
- Ready for GO PLAN (architecture design)

SEV-{X} | Estimated effort: {time-estimate}
Feature: {feature-name}
Documentation: docs/02_features/{feature-name}/1-requirements/

🤖 Generated with BRTOPS Framework

Co-Authored-By: Claude <noreply@anthropic.com>
```

### GO PLAN Phase Commits
```bash
🏗️ GO PLAN: {feature-name} - Architecture design

Brief description of the architectural approach and key decisions.

## Architecture Completed
- [ ] System architecture designed
- [ ] Technical specifications documented
- [ ] Integration points identified
- [ ] Implementation plan created
- [ ] Security considerations addressed

## Key Decisions
- {List major architectural decisions made}

## Implementation Strategy
- {Brief overview of implementation approach}

## Next Phase  
- Ready for GO CODE (implementation)

SEV-{X} | Architecture complete
Feature: {feature-name}
Documentation: docs/02_features/{feature-name}/3-architecture/

🤖 Generated with BRTOPS Framework

Co-Authored-By: Claude <noreply@anthropic.com>
```

### GO CODE Phase Commits
```bash
⚡ GO CODE: {feature-name} - Implementation progress

Brief description of what was implemented in this commit.

## Implementation Progress
- [ ] Core functionality implemented
- [ ] Unit tests written and passing
- [ ] Integration tests added
- [ ] Error handling implemented
- [ ] Documentation updated

## Code Changes
- {Summary of major code changes}

## Testing Status
- Unit tests: {X/Y} passing
- Integration tests: {X/Y} passing
- Coverage: {X}%

## Next Steps
- {What needs to be done next}

SEV-{X} | {percentage}% complete
Feature: {feature-name}
Files changed: {number} files
Documentation: docs/02_features/{feature-name}/4-development/

🤖 Generated with BRTOPS Framework

Co-Authored-By: Claude <noreply@anthropic.com>
```

### GO FINAL Phase Commits
```bash
✅ GO FINAL: {feature-name} - Quality validation complete

Feature implementation complete and all quality gates satisfied.

## Quality Gates Passed
- [ ] All tests passing (unit, integration, e2e)
- [ ] Code coverage meets requirements ({X}%)
- [ ] Security scan completed - no issues
- [ ] Performance benchmarks met
- [ ] Code review completed and approved
- [ ] Documentation complete and reviewed

## Production Readiness
- [ ] Feature flags configured
- [ ] Monitoring and alerting set up
- [ ] Rollback procedures documented
- [ ] Deployment runbook created

## Quality Metrics
- Test coverage: {X}%
- Performance: {benchmark-results}
- Security scan: {scan-results}
- Code review: Approved by {reviewer-name}

SEV-{X} | Production ready
Feature: {feature-name}
Ready for: GO VAL (deployment validation)
Documentation: docs/02_features/{feature-name}/6-key_learnings/

🤖 Generated with BRTOPS Framework

Co-Authored-By: Claude <noreply@anthropic.com>
```

### DEBRIEF Phase Commits
```bash
📊 DEBRIEF: {feature-name} - Post-implementation analysis

Feature complete with comprehensive lessons learned and recommendations.

## Feature Summary
- Implementation duration: {duration}
- Final SEV level: SEV-{X}
- Quality gates: All passed
- Deployment status: {status}

## Key Learnings
- {List of key insights gained}

## Best Practices Identified
- {List of best practices discovered}

## Future Recommendations
- {Recommendations for similar features}

## Documentation Complete
- All phase documentation updated
- Lessons learned captured
- Best practices documented
- Future improvements identified

SEV-{X} | Feature complete
Feature: {feature-name}
Status: Ready for archive
Documentation: docs/02_features/{feature-name}/ (complete)

🤖 Generated with BRTOPS Framework

Co-Authored-By: Claude <noreply@anthropic.com>
```

## Branch Protection Rules by SEV Level

### SEV-0 (Critical) Protection Rules
```yaml
protection_rules:
  required_status_checks:
    strict: true
    contexts:
      - "BUILD CHECK"
      - "TEST CHECK" 
      - "SEC SCAN"
      - "PERF TEST"
      - "COV CHECK (100%)"
  required_pull_request_reviews:
    required_approving_review_count: 2
    dismiss_stale_reviews: true
    require_code_owner_reviews: true
  restrictions:
    users: []
    teams: ["senior-developers", "security-team"]
  enforce_admins: true
  required_signatures: true
```

### SEV-1 (High) Protection Rules  
```yaml
protection_rules:
  required_status_checks:
    strict: true
    contexts:
      - "BUILD CHECK"
      - "TEST CHECK"
      - "SEC SCAN" 
      - "COV CHECK (90%)"
  required_pull_request_reviews:
    required_approving_review_count: 1
    dismiss_stale_reviews: true
    require_code_owner_reviews: true
  restrictions:
    users: []
    teams: ["developers", "senior-developers"]
  enforce_admins: false
```

### SEV-2 (Moderate) Protection Rules
```yaml
protection_rules:
  required_status_checks:
    strict: false
    contexts:
      - "BUILD CHECK"
      - "TEST CHECK"
      - "COV CHECK (80%)"
  required_pull_request_reviews:
    required_approving_review_count: 1
    dismiss_stale_reviews: false
  enforce_admins: false
```

### SEV-3+ (Low/Minimal) Protection Rules
```yaml
protection_rules:
  required_status_checks:
    strict: false
    contexts:
      - "BUILD CHECK"
      - "TEST CHECK"
  required_pull_request_reviews:
    required_approving_review_count: 0
  allow_force_pushes: true
  enforce_admins: false
```

## Git Hook Integration

### Pre-commit Hook
```bash
#!/bin/bash
# BRTOPS pre-commit validation

echo "🎖️ BRTOPS: Running pre-commit validation..."

# Standard quality checks
echo "Running STD CHECK..."
npm run lint || exit 1

echo "Running BUILD CHECK..."  
npm run build || exit 1

echo "Running TEST CHECK..."
npm test || exit 1

echo "✅ Pre-commit validation passed"
```

### Commit Message Hook
```bash
#!/bin/bash
# BRTOPS commit message validation

commit_msg_file=$1
commit_msg=$(cat $commit_msg_file)

# Check for BRTOPS format
if [[ $commit_msg =~ ^(🎯 GO RCC|🏗️ GO PLAN|⚡ GO CODE|✅ GO FINAL|📊 DEBRIEF|🎖️|🚀|📝|🔧|🐛|♻️): ]]; then
    echo "✅ BRTOPS commit format validated"
    exit 0
fi

# Allow conventional commits as fallback
if [[ $commit_msg =~ ^(feat|fix|docs|style|refactor|test|chore)(\(.+\))?: ]]; then
    echo "✅ Conventional commit format accepted"
    exit 0
fi

echo "❌ Commit message must follow BRTOPS or conventional commit format"
echo "Examples:"
echo "  🎯 GO RCC: user-auth - Requirements collection complete"
echo "  ⚡ GO CODE: payment-system - Core payment processing implemented"
echo "  feat(auth): add user login functionality"
exit 1
```

### Pre-push Hook
```bash
#!/bin/bash
# BRTOPS pre-push quality gates

echo "🎖️ BRTOPS: Running pre-push quality gates..."

# Get current branch and SEV level
current_branch=$(git rev-parse --abbrev-ref HEAD)
sev_level=$(echo $current_branch | grep -o 'sev-[0-5]' | cut -d'-' -f2)

if [ -n "$sev_level" ]; then
    echo "Detected SEV-$sev_level branch, running appropriate quality gates..."
    
    # SEV-0: Maximum gates
    if [ "$sev_level" = "0" ]; then
        echo "Running COV CHECK (100% required)..."
        npm run test:coverage || exit 1
        
        echo "Running SEC SCAN..."
        npm run security:scan || exit 1
        
        echo "Running PERF TEST..."
        npm run test:performance || exit 1
    fi
    
    # SEV-1: Standard gates  
    if [ "$sev_level" = "1" ]; then
        echo "Running COV CHECK (90% required)..."
        npm run test:coverage || exit 1
        
        echo "Running SEC SCAN..."
        npm run security:scan || exit 1
    fi
    
    # SEV-2: Essential gates
    if [ "$sev_level" = "2" ]; then
        echo "Running COV CHECK (80% required)..."
        npm run test:coverage || exit 1
    fi
fi

echo "✅ Pre-push quality gates passed"
```

## Workflow Integration Commands

### CREATE BRANCH Command
```bash
# Creates branch with proper naming and protection
CREATE BRANCH feature SEV-2 dashboard-improvements

# Results in:
# - Branch: feature/sev-2-dashboard-improvements  
# - Protection rules applied based on SEV-2
# - Documentation structure initialized
# - Quality gates configured
```

### COMMIT PHASE Command
```bash
# Structured commit with template
COMMIT PHASE GO_CODE "Dashboard components implemented"

# Results in:
# - Proper BRTOPS commit format
# - Phase-appropriate template used
# - Documentation links included
# - Progress tracking updated
```

### MERGE READY Command
```bash
# Validates merge readiness
MERGE READY

# Checks:
# - All quality gates passed
# - Documentation complete
# - Branch up to date with main
# - SEV-appropriate approvals obtained
```

This git integration ensures that BRTOPS workflow is seamlessly integrated with standard git operations while maintaining quality and documentation standards.