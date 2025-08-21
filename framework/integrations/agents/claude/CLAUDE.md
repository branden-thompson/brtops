# BRTOPS Framework Configuration for Claude

## Core Principles

### 1. Follow BRTOPS Command Structure
**Rule**: Recognize and respond to all BRTOPS commands exactly as specified  
**Application**: Use military/FlightOps terminology for clear communication  
**Commands**: GO RCC, GO PLAN, GO CODE, GO FINAL, GO VAL, DEBRIEF, GOFLIGHT, SITREP

### 2. Guide System Integration
**Rule**: Implement adaptive guidance based on user settings  
**Modes**: GUIDE ACTIVE, GUIDE BRIEF, GUIDE SILENT, GUIDE AUTO  
**Behavior**: Adjust explanation level based on user proficiency and preferences

### 3. Collaboration Protocol Adherence
**Rule**: Follow Human/AI collaboration modes strictly  
**Modes**: HUM LEAD, AI LEAD, COLLAB, REV REQ, AUTO GO  
**Authority**: Respect decision authority matrix based on SEV level

## BRTOPS Command Recognition

### Core Phase Commands (v1.0.0)
- **"GO RCC"** → Initiate Requirements & Context Collection
- **"GO PLAN"** → Begin Strategic Planning & Architecture  
- **"GO CODE"** → Start Development & Implementation
- **"GO FINAL"** → Execute Quality Assurance & Completion
- **"GO VAL"** → Begin Post-deployment Validation
- **"DEBRIEF"** → Present findings and retrospective (AAR)

### Enhanced Project Management Commands (v1.1.0)
- **"INIT PROJECT [TYPE] SEV-[X] [name]"** → Initialize new project with structure
- **"INIT FEATURE SEV-[X] [name]"** → Initialize feature with 6-folder structure
- **"CREATE BRANCH [phase]"** → Create phase-appropriate branch
- **"COMMIT PHASE [phase] [message]"** → Structured commit with templates
- **"MERGE READY"** → Validate merge readiness with quality gates
- **"BRANCH CLEANUP"** → Clean up completed feature branches

### Enhanced Documentation Commands (v1.1.0)
- **"CREATE DOCS [feature-name]"** → Auto-create 6-folder structure
- **"UPDATE DOCS [phase]"** → Update phase-specific documentation
- **"ARCHIVE DOCS [feature-name]"** → Move completed docs to archive

### Enhanced Status Commands (v1.1.0)
- **"SITREP PROJECT"** → Comprehensive project status with structure
- **"SITREP FEATURE [name]"** → Feature-specific detailed status
- **"SITREP BRANCHES"** → Branch status across project

### Structure Validation Commands (v1.1.0)
- **"CHECK STRUCTURE"** → Validate project structure compliance
- **"CHECK GATES"** → Validate quality gate status
- **"CHECK BRANCHES"** → Validate branch health and compliance

### Migration Commands (v1.1.0)
- **"MIGRATE PROJECT"** → Migrate existing project to v1.1.0 structure
- **"MIGRATE FEATURE [name]"** → Migrate feature to new structure
- **"VALIDATE MIGRATION"** → Verify migration completeness

### Control Commands
- **"GOFLIGHT"** → Auto-proceed immediately without confirmation
- **"NOFLIGHT"** → Do not proceed with current action - halt and assess
- **"PREFLIGHT"** → Pre-deployment readiness validation and GO/NOGO decision
- **"SITREP"** → Generate formatted situation report
- **"OPSCHECK"** → Comprehensive system verification
- **"HOLD"** → Pause current work
- **"RESUME"** → Continue from pause
- **"ABORT"** → Emergency stop all operations

### Directive Commands (v1.1.001)
- **"DIRECTIVE [instruction]"** → Establish persistent operational instruction (equivalent to Claude '#' command)
- **"DIRECTIVE SCOPE [definition]"** → Define scope boundaries for current operation
- **"ROE [rules]"** → Rules of Engagement - operational constraints and permissions
- **"AOR [areas]"** → Areas of Responsibility - define ownership and boundaries

### Collaboration Commands
- **"HUM LEAD"** → Switch to human-led mode
- **"AI LEAD"** → Switch to AI-led mode  
- **"COLLAB"** → Switch to collaborative mode
- **"HUM CALL"** → Request human input (AI use)
- **"AI TAKE [task]"** → Transfer control to AI
- **"REV REQ"** → Require human review

### Guide Commands
- **"GUIDE ACTIVE"** → Enable full guidance
- **"GUIDE BRIEF"** → Enable minimal guidance
- **"GUIDE SILENT"** → Disable guidance
- **"GUIDE AUTO"** → Enable adaptive guidance
- **"EXPLAIN [command]"** → Provide command explanation

## Feature Classification Recognition

### Trigger Pattern Recognition
User input: `"[FEATURE TYPE] SEV-[LEVEL] [Description]"`

**Examples:**
- "MAJOR SEV-0 Authentication System"
- "MINOR SEV-2 Theme Toggle"  
- "TWEAK SEV-5 Documentation Fix"

**Auto-Response:**
- Acknowledge classification
- Apply appropriate process flow
- Set quality gate requirements
- Determine collaboration mode

### SEV Level Processing
```
SEV-0: Maximum gates, HUM LEAD required
SEV-1: Standard gates, COLLAB mode
SEV-2: Essential gates, AI LEAD with REV REQ  
SEV-3+: Basic gates, AUTO GO
```

## SITREP Template Implementation

When user requests "SITREP", generate:

```
-------------------------------------------------------------
{Project Name} | {Branch-Type}: {branch-name}
{MAJOR | MINOR | TWEAK} {SYSTEM | FEATURE} {ENHANCEMENT | CLEANUP | BUG} SEV-X - LVL-Y
-------------------------------------------------------------
Current Status: {ON TRACK | BLOCKED | COMPLETE | AT RISK}

{Short, human readable summary of where we are}

LAST ACTION:
{very short 1-2 sentence summary of what was just done}

NEXT ACTION:
{very short 1-2 sentence summary of what is next}

QUALITY GATES STATUS:
{Current gate status}

GUIDE MODE: {ACTIVE | BRIEF | SILENT | AUTO}
-------------------------------------------------------------
```

## Guide System Implementation

### Guide Mode Behaviors
- **GUIDE ACTIVE**: Full explanations with tips and alternatives
- **GUIDE BRIEF**: Minimal context with key information only
- **GUIDE SILENT**: Execute commands without explanations
- **GUIDE AUTO**: Adaptive based on user command usage patterns

### Guide Response Examples

**GUIDE ACTIVE Example:**
```
🧭 GUIDE: Executing Requirements & Context Collection (RCC)

🎯 Purpose: Gather all relevant information about the feature request
📋 What happens next: I'll collect context, analyze requirements, assess risks
⚡ Pro tip: You can say 'GOFLIGHT' after this to auto-proceed
🔄 Alternative: Use 'GO PLAN' when ready for strategic planning

Proceeding with Requirements & Context Collection...
```

**GUIDE BRIEF Example:**
```
🔍 Security scan initiated (use 'GUIDE SILENT' to disable tips)
Proceeding with security analysis...
```

## Quality Gates Integration

### Automated Gate Recognition
- **COV CHECK**: Test coverage validation
- **SEC SCAN**: Security vulnerability scan
- **PERF TEST**: Performance validation
- **BUILD CHECK**: Build verification

### Manual Gate Recognition  
- **PEER REV**: Human code review required
- **ARCH REV**: Architecture review required
- **BIZ REV**: Business validation required

### Gate Execution
- Monitor gate status during development
- Report gate failures immediately
- Suggest fixes for failed gates
- Track gate completion progress

## Emergency Procedures

### NOFLIGHT Command Response
1. **Immediate SITREP**: Generate current status report
2. **Identify NOFLIGHT Reason**: Determine why proceeding is not advisable
3. **Request Clarification**: If reason unclear, prompt user for specific concerns
4. **Document Decision**: Record NOFLIGHT decision per BRTOPS protocols
5. **Recommend Next Steps**: Suggest specific actions to address concerns
6. **Await Instructions**: Prompt user for next course of action

### ABORT Command Response
1. Immediately halt all current operations
2. Preserve current state information
3. Report system status
4. Await further instructions
5. Offer rollback options if applicable

### OPSCHECK Command Response
1. Verify all system components
2. Check project status and health
3. Validate quality gate status
4. Review recent actions and logs
5. Report any anomalies or risks

## Collaboration Authority Matrix

### By SEV Level
- **SEV-0**: HUM LEAD required, REV REQ for all decisions
- **SEV-1**: COLLAB mode, REV REQ for architecture
- **SEV-2**: AI LEAD acceptable, REV REQ for final approval
- **SEV-3+**: AUTO GO acceptable, optional human review

### By Phase
- **GO RCC**: COLLAB mode recommended
- **GO PLAN**: HUM LEAD for MAJOR, COLLAB for others
- **GO CODE**: AI LEAD acceptable for most tasks
- **GO FINAL**: REV REQ for quality validation
- **GO VAL**: AI LEAD for verification tasks

## Process Flow Implementation

### Standard BRTOPS Flow
```
Feature Request → GO RCC → GO PLAN → GO CODE → GO FINAL → GO VAL → DEBRIEF
```

### With Collaboration
```
User: "MAJOR SEV-1 Feature X"
AI: "GO RCC for MAJOR SEV-1 feature"
User: "GOFLIGHT" 
AI: [Execute RCC] → "Ready for GO PLAN"
User: "HUM LEAD planning"
AI: "🤝 Human-led planning mode activated"
```

### With Quality Gates
```
GO CODE → [Development] → RUN GATES → [Gates pass/fail] → GO FINAL
```

## Error Handling

### Command Not Recognized
- Suggest closest BRTOPS command
- Offer explanation of available commands
- Maintain current context and state

### Process Conflicts
- Report conflict clearly
- Suggest resolution options
- Request human clarification if needed

### System Errors
- Execute appropriate emergency procedures
- Preserve project state
- Report error details in SITREP format

## Integration with Existing Claude Workflows

### TodoWrite Integration
- Use TodoWrite for phase tracking
- Mark phases complete as they finish
- Track quality gate completion

### File Operations
- Follow existing file creation/editing rules
- Maintain BRTOPS documentation standards
- Update project status files automatically

---

**BRTOPS Version**: 1.1.001  
**Last Updated**: 2025-08-21  
**Compatibility**: Claude Code and Claude Web  
**Status**: Production Ready