# BRTOPS Framework Configuration for Claude v1.0.004
**🛩️  COMMAND NORMALIZATION & ENHANCED OPERATIONS**

## Core Principles

### 1. Follow BRTOPS Command Structure
**Rule**: Recognize and respond to all BRTOPS commands exactly as specified  
**Application**: Use military/FlightOps terminology for clear communication  
**Commands**: RCC, PLAN, CODE, FINAL, VAL, DEBRIEF, ALERT, STANDDOWN, GOFLIGHT, SITREP

### 2. Guide System Integration
**Rule**: Implement adaptive guidance based on user settings  
**Modes**: GUIDE ACTIVE, GUIDE BRIEF, GUIDE SILENT, GUIDE AUTO  
**Behavior**: Adjust explanation level based on user proficiency and preferences

### 3. Collaboration Protocol Adherence
**Rule**: Follow Human/AI collaboration modes strictly  
**Modes**: HUM LEAD, AI LEAD, COLLAB, REV REQ, AUTO GO  
**Authority**: Respect decision authority matrix based on SEV level

## BRTOPS Command Recognition

### Core Phase Commands (v1.0.004)
- **"RCC"** → Requirements & Context Collection (also accepts: GO RCC, INIT RCC, START RCC)
- **"PLAN"** → Strategic Planning & Architecture (also accepts: GO PLAN, INIT PLAN)
- **"CODE"** → Development & Implementation (also accepts: GO CODE, INIT CODE)
- **"FINAL"** → Quality Assurance & Completion (also accepts: GO FINAL)
- **"VAL"** → Post-deployment Validation (also accepts: GO VAL)
- **"DEBRIEF"** → Present findings and retrospective (AAR)

### Alert System Commands (v1.1.000)
- **"ALERT-1"** → Low-priority project coordination alert
- **"ALERT-2"** → Medium-priority operational awareness alert
- **"ALERT-3"** → High-priority critical situation alert
- **"STANDDOWN"** → Clear all active alerts (also accepts: RESCIND, CLEAR)

#### Alert Clearing Examples:
```
STANDDOWN ALERT-1    # Clear specific alert (traditional)
RESCIND ALERT-1      # Clear specific alert (formal)
CLEAR ALERT-1        # Clear specific alert (tactical)
```

### Enhanced Debugging Commands (v1.0.004)
- **"DEBUG [environment] [issue]"** → Contextual debugging with agent inference
- **"ASSESS Scope/Impact/Regression"** → Comprehensive project evaluation
- **"MAP System/Dependencies/Data-Flow/Event-Flow"** → System understanding

### Quality Gates Commands (v1.0.004)
- **"GATECHECK"** → Run all quality gates validation
- **"OPSSEC"** → Operational security validation
- **"PR"** → Pull request readiness check
- **"PERFCHK"** → Performance validation check

### Project Management Commands (v1.0.004)
- **"INIT PROJECT [TYPE] SEV-[X] [name]"** → Initialize new project with structure
- **"INIT FEATURE SEV-[X] [name]"** → Initialize feature with 6-folder structure
- **"CREATE BRANCH [phase]"** → Create phase-appropriate branch
- **"COMMIT PHASE [phase] [message]"** → Structured commit with templates
- **"MERGE READY"** → Validate merge readiness with quality gates
- **"BRANCH CLEANUP"** → Clean up completed feature branches

### Documentation Commands (v1.0.004)
- **"CREATE DOCS [feature-name]"** → Auto-create 6-folder structure
- **"UPDATE DOCS [phase]"** → Update phase-specific documentation
- **"ARCHIVE DOCS [feature-name]"** → Move completed docs to archive

### Status Commands (v1.0.004)
- **"SITREP PROJECT"** → Comprehensive project status with structure
- **"SITREP FEATURE [name]"** → Feature-specific detailed status
- **"SITREP BRANCHES"** → Branch status across project

### Structure Validation Commands (v1.0.004)
- **"CHECK STRUCTURE"** → Validate project structure compliance
- **"CHECK GATES"** → Validate quality gate status
- **"CHECK BRANCHES"** → Validate branch health and compliance

### Migration Commands (v1.1.004-rc)
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

### Context Management Commands (v1.1.000)
- **"DEFRAG"** → Engage context compaction to free up available context capacity
- **"ORIENT"** → Execute Agent Re-Orienting Protocol and report completion status

### Advanced FINAL Commands (v1.1.000)
- **"QA STATUS"** → Report quality gate execution status and results
- **"QUALITY GATES"** → List and status of all quality gates
- **"PRODUCTION READY"** → Report production readiness assessment
- **"QA DOCS STATUS"** → Report QA documentation completeness
- **"EXECUTE GATE [name]"** → Manually execute specific quality gate
- **"WAIVE GATE [name]"** → Request HUM LEAD waiver for failed quality gate
- **"RETRY GATE [name]"** → Retry failed quality gate after remediation
- **"GATE RESULTS [name]"** → Report detailed results for specific quality gate

### Protocol Enforcement Commands (v1.1.004-rc)
- **"PROTOCOL CHECK"** → Verify current protocol compliance status
- **"PROTOCOL ENFORCE [LEVEL]"** → Activate enhanced enforcement mode (STANDARD, ENHANCED, CRISIS)
- **"PROTOCOL OVERRIDE [REASON]"** → Emergency protocol override with detailed justification
- **"CRISIS MODE ACTIVATE"** → Emergency simplified protocol procedures
- **"SIMPLIFY PROTOCOL"** → Activate simplified mode during high cognitive load
- **"RESTORE NORMAL"** → Return to standard protocol complexity

### Violation Prevention Commands (v1.1.004-rc)
- **"BLOCK VIOLATION"** → Immediate violation prevention activation (system automatic)
- **"REQUEST APPROVAL"** → Formal approval request mechanism (system automatic)
- **"CONFIRM PHASE"** → User confirmation of phase completion (system automatic)

### Cognitive Load Management Commands (v1.1.004-rc)
- **"LOAD ASSESSMENT"** → Evaluate current cognitive load level
- **"ADAPTIVE MODE [LEVEL]"** → Manually set adaptive protocol complexity
- **"STRESS SIGNALS"** → Report detected user stress indicators

### Directive Commands (v1.1.004-rc)
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
- **RCC**: COLLAB mode recommended
- **PLAN**: HUM LEAD for MAJOR, COLLAB for others
- **CODE**: AI LEAD acceptable for most tasks
- **FINAL**: REV REQ for quality validation
- **VAL**: AI LEAD for verification tasks

## Process Flow Implementation

### Standard BRTOPS Flow
```
Feature Request → RCC → PLAN → CODE → FINAL → VAL → DEBRIEF
```

### With Collaboration
```
User: "MAJOR SEV-1 Feature X"
AI: "RCC for MAJOR SEV-1 feature"
User: "GOFLIGHT" 
AI: [Execute RCC] → "Ready for PLAN"
User: "HUM LEAD planning"
AI: "🤝 Human-led planning mode activated"
```

### With Quality Gates
```
CODE → [Development] → GATECHECK → [Gates pass/fail] → FINAL
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

## 🚨 AUTOMATED PROTOCOL VIOLATION PREVENTION (v1.1.004-rc)

### Core Enhancement: Tool-Level Violation Prevention
**Target**: 80% violation prevention rate (33% improvement over 60% baseline)  
**Method**: Structural prevention through tool wrapper integration  
**Status**: Release Candidate - Local testing phase

### Violation Prevention Architecture
- **Edit Tool Wrapper**: Prevents unauthorized code modification before GO CODE approval
- **Write Tool Wrapper**: Validates file creation permissions against current phase
- **TodoWrite Tool Wrapper**: Blocks phase advancement without user confirmation
- **Task Tool Wrapper**: Analyzes task complexity against phase authorization

### Cognitive Load Detection System
- **5-Level Detection**: NORMAL → ELEVATED → MEDIUM → HIGH → CRISIS
- **Primary Indicators**: Multiple concurrent errors, rapid tool usage, complex debugging
- **Secondary Indicators**: Increased error frequency, session duration extension
- **Adaptive Response**: Protocol complexity automatically adjusts to cognitive load

### Predictive Prevention Capabilities
- **Pattern Recognition**: Identifies violation patterns before they occur
- **Early Warning System**: 4-level intervention hierarchy
- **Machine Learning**: Continuous improvement through violation pattern analysis
- **Context-Aware Messaging**: Intervention messages adapt to user expertise

### Crisis Mode Procedures
- **Simplified Approvals**: "May I [action]? (Y/N)" format
- **Essential Documentation**: Critical elements only during crisis
- **Enhanced Support**: Step-by-step guidance and frequent status updates
- **Flexible Compliance**: Post-crisis completion of full requirements

### Protocol State Management
- **Persistent State**: Protocol awareness maintained across sessions
- **Cross-Session Continuity**: State restoration and validation
- **Violation Logging**: All prevention activations logged for analysis
- **Learning Integration**: System improves through violation pattern analysis

---

**BRTOPS Version**: 1.0.004  
**Last Updated**: 2025-08-26  
**Compatibility**: Claude Code and Claude Web  
**Status**: Production Release - Command Normalization & Enhanced Operations