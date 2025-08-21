# BRTOPS Command Reference v1.0.000

## Phase Commands

### GO RCC (Requirements & Context Collection)
**Purpose**: Start discovery phase to gather requirements and context  
**Usage**: `GO RCC`  
**Normal**: "Start Discovery"  
**Next**: GO PLAN or GOFLIGHT  
**Authority**: Any user  

### GO PLAN (Strategic Planning)
**Purpose**: Begin strategic planning and architecture design  
**Usage**: `GO PLAN`  
**Normal**: "Start Planning"  
**Next**: GO CODE or GOFLIGHT  
**Authority**: Any user  

### GO CODE (Implementation)
**Purpose**: Start development and implementation phase  
**Usage**: `GO CODE`  
**Normal**: "Start Implementation"  
**Next**: GO FINAL or GOFLIGHT  
**Authority**: Any user  

### GO FINAL (Quality Assurance)
**Purpose**: Execute quality assurance and completion tasks  
**Usage**: `GO FINAL`  
**Normal**: "Start Finalization"  
**Next**: GO VAL or GOFLIGHT  
**Authority**: Any user  

### GO VAL (Post-deployment Validation)
**Purpose**: Start post-deployment validation and verification  
**Usage**: `GO VAL`  
**Normal**: "Start Validation"  
**Next**: DEBRIEF  
**Authority**: Any user  

### DEBRIEF (Retrospective)
**Purpose**: Present findings and conduct retrospective using AAR  
**Usage**: `DEBRIEF`  
**Normal**: "Retrospective"  
**Next**: Project completion  
**Authority**: Any user  

## Control Commands

### GOFLIGHT
**Purpose**: Auto-proceed authorization - continue immediately without confirmation  
**Usage**: `GOFLIGHT`  
**Context**: Flight operations terminology  
**Authority**: Any user  

### SITREP (Situation Report)
**Purpose**: Get current project status report  
**Usage**: `SITREP`  
**Normal**: "Current Status"  
**Output**: Formatted project status with recent actions and next steps  
**Authority**: Any user  

### OPSCHECK
**Purpose**: Comprehensive system status verification  
**Usage**: `OPSCHECK`  
**Context**: Operations check terminology  
**Authority**: Any user  

### HOLD
**Purpose**: Pause current work  
**Usage**: `HOLD`  
**Pair**: RESUME  
**Authority**: Any user  

### RESUME
**Purpose**: Continue from pause  
**Usage**: `RESUME`  
**Pair**: HOLD  
**Authority**: Any user  

### ABORT
**Purpose**: Emergency stop all operations  
**Usage**: `ABORT`  
**Authority**: Any user  

### RESET
**Purpose**: Start over from beginning  
**Usage**: `RESET`  
**Authority**: Any user  

## Collaboration Commands

### HUM LEAD (Human Lead)
**Purpose**: Switch to human-led collaboration mode  
**Usage**: `HUM LEAD`  
**Context**: Human drives decisions, AI assists  
**Authority**: Human user  

### AI LEAD (AI Lead)
**Purpose**: Switch to AI-led collaboration mode  
**Usage**: `AI LEAD`  
**Context**: AI drives process, human validates  
**Authority**: Human user  

### COLLAB (Collaborative)
**Purpose**: Switch to equal partnership mode  
**Usage**: `COLLAB`  
**Context**: Equal partnership approach  
**Authority**: Any user  

### HUM CALL (Human Call)
**Purpose**: Request human input  
**Usage**: `HUM CALL: [description]`  
**Context**: AI needs human decision  
**Authority**: AI agent  

### AI TAKE (AI Take)
**Purpose**: Transfer control to AI  
**Usage**: `AI TAKE [task]`  
**Context**: Human delegates to AI  
**Authority**: Human user  

### REV REQ (Review Required)
**Purpose**: Mandatory human approval needed  
**Usage**: `REV REQ`  
**Context**: Critical changes  
**Authority**: AI agent  

### AUTO GO (Auto Proceed)
**Purpose**: AI authorized to continue  
**Usage**: `AUTO GO`  
**Context**: Routine operations  
**Authority**: Human user  

## Guide Commands

### GUIDE ACTIVE
**Purpose**: Enable full guidance mode  
**Usage**: `GUIDE ACTIVE`  
**Context**: Provides tips, explanations, and context for all commands  
**Authority**: Any user  

### GUIDE BRIEF
**Purpose**: Enable minimal guidance mode  
**Usage**: `GUIDE BRIEF`  
**Context**: Only provide tips for new/unfamiliar commands  
**Authority**: Any user  

### GUIDE SILENT
**Purpose**: Disable guidance mode  
**Usage**: `GUIDE SILENT`  
**Context**: Execute commands without explanations  
**Authority**: Any user  

### GUIDE AUTO
**Purpose**: Enable adaptive guidance mode  
**Usage**: `GUIDE AUTO`  
**Context**: Learn user familiarity and adjust tips accordingly  
**Authority**: Any user  

### EXPLAIN [COMMAND]
**Purpose**: Get explanation for specific command  
**Usage**: `EXPLAIN GO RCC`  
**Context**: On-demand command help  
**Authority**: Any user  

## Quality Gate Commands

### RUN GATES
**Purpose**: Execute all required quality gates  
**Usage**: `RUN GATES`  
**Context**: Auto-determined by SEV level  
**Authority**: Any user  

### GATE STATUS
**Purpose**: Check current gate status  
**Usage**: `GATE STATUS`  
**Output**: Shows pass/fail for all gates  
**Authority**: Any user  

### COV CHECK (Coverage Check)
**Purpose**: Test coverage validation  
**Usage**: `COV CHECK`  
**Trigger**: Before GO FINAL  
**Authority**: Automated  

### SEC SCAN (Security Scan)
**Purpose**: Security vulnerability scan  
**Usage**: `SEC SCAN`  
**Trigger**: Before deployment  
**Authority**: Automated  

### PEER REV (Peer Review)
**Purpose**: Human code review  
**Usage**: `PEER REV`  
**Trigger**: All implementations  
**Authority**: Human reviewer  

### PERF TEST (Performance Test)
**Purpose**: Performance validation  
**Usage**: `PERF TEST`  
**Trigger**: Resource-heavy features  
**Authority**: Automated  

## Feature Classification

### Feature Types
- **MAJOR**: Complex features requiring full lifecycle
- **MINOR**: Standard features with streamlined process  
- **TWEAK**: Simple modifications

### SEV Levels
- **SEV-0**: Critical impact/extreme complexity
- **SEV-1**: High impact/high complexity
- **SEV-2**: Moderate impact/moderate complexity
- **SEV-3**: Low impact/low complexity
- **SEV-4**: Minimal impact/minimal complexity
- **SEV-5**: Trivial impact/trivial complexity

### Usage Pattern
```
[FEATURE TYPE] SEV-[LEVEL] [Description]

Examples:
"MAJOR SEV-0 User Authentication System"
"MINOR SEV-2 Theme Toggle Implementation"
"TWEAK SEV-5 Fix Documentation Typo"
```

## Process Integration

### Standard Flow
```
Feature Request → GO RCC → GO PLAN → GO CODE → GO FINAL → GO VAL → DEBRIEF
```

### With Quality Gates
```
GO CODE → RUN GATES → GO FINAL → PEER REV → RUN GATES → GO VAL
```

### Emergency Flow
```
ABORT → ASSESS → ROLLBACK → RESUME or RESET
```

## Command Combinations

### Typical Workflow
```
User: "MAJOR SEV-1 User Dashboard Enhancement"
AI: "GO RCC for MAJOR SEV-1 feature"
User: "GOFLIGHT"
AI: [Proceeds through phases]
User: "SITREP"
AI: [Shows current status]
```

### Collaboration Example
```
User: "HUM LEAD architecture decisions"
AI: "🤝 Human-led mode activated"
User: "AI TAKE implementation tasks"  
AI: "🤖 Taking control of implementation"
```

### Emergency Example
```
User: "OPSCHECK"
AI: [Comprehensive system verification]
User: "ABORT" (if issues found)
AI: [Emergency stop all operations]
```