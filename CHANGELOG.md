# CHANGELOG - BRTOPS Framework

All notable changes to the BRTOPS framework are documented in this file.

## [1.1.001] - 2025-08-21 - Directive Commands Addition

### ✨ Added
- **Directive Commands System**
  - `DIRECTIVE [instruction]` - Establish persistent operational instructions (equivalent to Claude '#' command)
  - `DIRECTIVE SCOPE [definition]` - Define scope boundaries for current operations
  - `ROE [rules]` - Rules of Engagement for operational constraints and permissions
  - `AOR [areas]` - Areas of Responsibility for ownership and boundary definition

### 🔧 Enhanced
- **Claude Integration** - Updated with directive command recognition patterns
- **Operational Control** - Enhanced command structure for better project governance

---

## [1.1.0] - 2025-08-21 - Structure & Workflow Enhancement

### ✨ Added
- **Enhanced Project Management Commands**
  - `INIT PROJECT [TYPE] SEV-[X] [name]` - Initialize complete project structure
  - `INIT FEATURE SEV-[X] [name]` - Initialize feature with 6-folder documentation structure
  - `CREATE BRANCH [phase]` - Create phase-appropriate branches with proper naming
  - `COMMIT PHASE [phase] [message]` - Structured commits with BRTOPS templates
  - `MERGE READY` - Validate merge readiness with quality gate compliance
  - `BRANCH CLEANUP` - Clean up completed feature branches

- **Advanced Documentation System**
  - Universal project structure template with complete folder hierarchy
  - 6-folder feature documentation system (requirements, analysis, architecture, development, debugging, key learnings)
  - `CREATE DOCS [feature-name]` - Auto-create documentation structure
  - `UPDATE DOCS [phase]` - Update phase-specific documentation
  - `ARCHIVE DOCS [feature-name]` - Archive completed feature documentation

- **Enhanced Status & Validation Commands**
  - `SITREP PROJECT` - Comprehensive project status with structure analysis
  - `SITREP FEATURE [name]` - Feature-specific detailed status reports
  - `SITREP BRANCHES` - Branch status across entire project
  - `CHECK STRUCTURE` - Validate project structure compliance
  - `CHECK GATES` - Validate quality gate status
  - `CHECK BRANCHES` - Validate branch health and compliance

- **Git Workflow Integration**
  - Branch naming conventions by SEV level (`feature/sev-{X}-{feature-name}`)
  - Phase-based commit templates for all BRTOPS phases
  - Branch protection rules based on SEV classification
  - Pre-commit, commit-msg, and pre-push hooks for quality enforcement
  - Quality gate automation based on SEV level requirements

- **Project Migration Tools**
  - `MIGRATE PROJECT` - Migrate existing projects to BRTOPS v1.1.0 structure
  - `MIGRATE FEATURE [name]` - Migrate specific features to new structure
  - `VALIDATE MIGRATION` - Verify migration completeness

- **Pre-Deployment Commands**
  - `PREFLIGHT` - Pre-deployment readiness checklist and validation
  - `NOFLIGHT` - Do not proceed with current action - halt and assess
  - Comprehensive audit of version references, documentation, and artifacts
  - GO/NOGO decision support with detailed findings and response protocols

### 🔧 Enhanced
- **Claude Integration**
  - Updated Claude BRTOPS configuration with all v1.1.0 commands
  - Enhanced command recognition patterns
  - Improved SITREP formatting with project structure awareness
  - Added structure validation integration

- **Quality Gate System**
  - SEV-specific quality gate requirements
  - Automated coverage, security, and performance gates
  - Software project-specific gate configurations
  - Integration with git hooks for automated enforcement

### 📋 Documentation Updates
- Enhanced command reference with all new v1.1.0 commands
- Complete project structure template documentation
- Git workflow integration guide with examples
- Software project configuration templates
- Migration procedures for existing projects

### 🔄 Backward Compatibility
- All BRTOPS v1.0.0 commands remain unchanged
- New commands are additive enhancements, not replacements
- Existing projects can be migrated using new migration tools

---

## [1.0.000] - 2025-08-20 - Foundation Release

### ✨ Added - Initial Framework
- Core command structure (GO RCC, GO PLAN, GO CODE, GO FINAL, GO VAL, DEBRIEF)
- Guide system with adaptive modes (GUIDE ACTIVE, GUIDE BRIEF, GUIDE SILENT, GUIDE AUTO)
- Collaboration protocols (HUM LEAD, AI LEAD, COLLAB, REV REQ, AUTO GO)
- SEV classification system (SEV-0 through SEV-5)
- Feature type classification (MAJOR, MINOR, TWEAK)
- Basic quality gate framework
- SITREP reporting system
- Emergency procedures (ABORT, OPSCHECK)
- Claude agent integration

### 📚 Documentation
- Complete command reference documentation
- Getting started guides
- Agent setup procedures
- Examples and case studies

---

**Version Format**: [MAJOR.MINOR.PATCH] following Semantic Versioning  
**Categories**: ✨ Added | 🔧 Enhanced | 🐛 Fixed | 📋 Documentation | 🔄 Changed