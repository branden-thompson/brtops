# BRTOPS v1.1.0 Enhanced Commands Reference

## New Project Management Commands

### INIT PROJECT [TYPE] SEV-[X] [name]
**Purpose**: Initialize new project with complete BRTOPS structure  
**Usage**: `INIT PROJECT SOFTWARE SEV-2 my-web-app`  
**Creates**: Full project structure, git repo, BRTOPS config  
**Project Types**: SOFTWARE, DOCS, RESEARCH, CREATIVE  

### INIT FEATURE SEV-[X] [name]
**Purpose**: Initialize feature within existing project  
**Usage**: `INIT FEATURE SEV-1 user-authentication`  
**Creates**: 6-folder structure, feature branch, documentation templates  

### CREATE BRANCH [phase]
**Purpose**: Create phase-appropriate branch with proper naming  
**Usage**: `CREATE BRANCH feature`  
**Naming**: `feature/sev-{X}-{feature-name}`  
**Integration**: Auto-sets up branch protection based on SEV level  

### COMMIT PHASE [phase] [message]
**Purpose**: Phase-specific structured commit with templates  
**Usage**: `COMMIT PHASE GO_RCC "User requirements collected"`  
**Format**: Uses BRTOPS commit templates with proper formatting  

### MERGE READY
**Purpose**: Prepare feature for merge with quality validation  
**Usage**: `MERGE READY`  
**Checks**: All quality gates, documentation complete, branch up-to-date  

### BRANCH CLEANUP
**Purpose**: Clean up completed feature branches  
**Usage**: `BRANCH CLEANUP`  
**Actions**: Archive documentation, remove merged branches, update tracking  

## Enhanced Documentation Commands

### CREATE DOCS [feature-name]
**Purpose**: Auto-create 6-folder feature documentation structure  
**Usage**: `CREATE DOCS user-dashboard`  
**Creates**: Complete folder hierarchy with templates  

### UPDATE DOCS [phase]
**Purpose**: Update phase-specific documentation with templates  
**Usage**: `UPDATE DOCS GO_PLAN`  
**Templates**: Phase-appropriate checklist and guidance  

### ARCHIVE DOCS [feature-name]
**Purpose**: Move completed feature docs to archive  
**Usage**: `ARCHIVE DOCS user-dashboard`  
**Actions**: Moves to archive, updates index, preserves links  

## Enhanced Status Commands

### SITREP PROJECT
**Purpose**: Comprehensive project status with structure analysis  
**Usage**: `SITREP PROJECT`  
**Output**: Project health, structure compliance, active features  

### SITREP FEATURE [name]
**Purpose**: Feature-specific detailed status report  
**Usage**: `SITREP FEATURE user-auth`  
**Output**: Feature progress, quality gates, documentation status  

### SITREP BRANCHES
**Purpose**: Branch status across entire project  
**Usage**: `SITREP BRANCHES`  
**Output**: Active branches, merge readiness, protection status  

## Structure Validation Commands

### CHECK STRUCTURE
**Purpose**: Validate project structure compliance  
**Usage**: `CHECK STRUCTURE`  
**Validation**: Folder structure, required files, template compliance  

### CHECK GATES
**Purpose**: Validate all quality gate status  
**Usage**: `CHECK GATES`  
**Validation**: SEV-appropriate gates, coverage, security, performance  

### CHECK BRANCHES
**Purpose**: Validate branch health and compliance  
**Usage**: `CHECK BRANCHES`  
**Validation**: Naming conventions, protection rules, merge readiness  

## Migration Commands

### MIGRATE PROJECT
**Purpose**: Migrate existing project to BRTOPS v1.1.0 structure  
**Usage**: `MIGRATE PROJECT`  
**Actions**: Creates missing structure, updates config, preserves existing  

### MIGRATE FEATURE [name]
**Purpose**: Migrate specific feature to new documentation structure  
**Usage**: `MIGRATE FEATURE user-auth`  
**Actions**: Reorganizes docs into 6-folder structure  

### VALIDATE MIGRATION
**Purpose**: Verify migration completeness and compliance  
**Usage**: `VALIDATE MIGRATION`  
**Checks**: Structure compliance, documentation integrity, git consistency  

### PREFLIGHT
**Purpose**: Pre-deployment readiness validation and GO/NOGO decision  
**Usage**: `PREFLIGHT`  
**Checks**: Version references, documentation completeness, artifact validation, release readiness  
**Output**: Comprehensive audit report with GOFLIGHT/NOFLIGHT recommendation

## Command Integration Patterns

### Typical New Feature Workflow
```bash
# Initialize feature
INIT FEATURE SEV-2 payment-integration

# Proceed through phases
GO RCC
# [Requirements work]
COMMIT PHASE GO_RCC "Payment requirements and user stories collected"

GO PLAN  
# [Architecture work]
COMMIT PHASE GO_PLAN "Payment system architecture and integration design"

GO CODE
# [Implementation work]
COMMIT PHASE GO_CODE "Payment processing core functionality implemented"

GO FINAL
# [Quality assurance]
COMMIT PHASE GO_FINAL "Payment integration ready for production"

# Prepare for merge
MERGE READY
# [Automated quality validation]

# Complete feature
BRANCH CLEANUP
```

### Project Initialization Workflow
```bash
# Start new project
INIT PROJECT SOFTWARE SEV-1 ecommerce-platform

# Verify structure
CHECK STRUCTURE
CHECK GATES

# Begin first feature
INIT FEATURE SEV-0 user-authentication
GO RCC
```

## Backward Compatibility

All BRTOPS v1.0.0 commands remain unchanged:
- GO RCC, GO PLAN, GO CODE, GO FINAL, GO VAL, DEBRIEF
- GOFLIGHT, SITREP, OPSCHECK, HOLD, RESUME, ABORT
- HUM LEAD, AI LEAD, COLLAB, HUM CALL, AI TAKE
- GUIDE ACTIVE, GUIDE BRIEF, GUIDE SILENT, GUIDE AUTO
- BAG TAG, AAR

New commands are additive enhancements, not replacements.